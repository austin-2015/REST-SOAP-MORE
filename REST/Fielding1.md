#### http://roy.gbiv.com/untangled/2008/rest-apis-must-be-hypertext-driven
#### REST APIs must be hypertext-driven
##### Posted by Roy T. Fielding under software architecture, web architecture 
##### Mon 20 Oct 2008
#### Contents of Blog QUOTED as below  
What needs to be done to make the REST architectural style clear on the notion that hypertext is a constraint? In other words, if the engine of application state (and hence the API) is not being driven by hypertext, then it cannot be RESTful and cannot be a REST API. Period. Is there some broken manual somewhere that needs to be fixed?

API designers, please note the following rules before calling your creation a REST API:

A REST API should not be dependent on any single communication protocol, though its successful mapping to a given protocol may be dependent on the availability of metadata, choice of methods, etc. In general, any protocol element that uses a URI for identification must allow any URI scheme to be used for the sake of that identification. [Failure here implies that identification is not separated from interaction.]
A REST API should not contain any changes to the communication protocols aside from filling-out or fixing the details of underspecified bits of standard protocols, such as HTTP’s PATCH method or Link header field. Workarounds for broken implementations (such as those browsers stupid enough to believe that HTML defines HTTP’s method set) should be defined separately, or at least in appendices, with an expectation that the workaround will eventually be obsolete. [Failure here implies that the resource interfaces are object-specific, not generic.]
A REST API should spend almost all of its descriptive effort in defining the media type(s) used for representing resources and driving application state, or in defining extended relation names and/or hypertext-enabled mark-up for existing standard media types. Any effort spent describing what methods to use on what URIs of interest should be entirely defined within the scope of the processing rules for a media type (and, in most cases, already defined by existing media types). [Failure here implies that out-of-band information is driving interaction instead of hypertext.]
A REST API must not define fixed resource names or hierarchies (an obvious coupling of client and server). Servers must have the freedom to control their own namespace. Instead, allow servers to instruct clients on how to construct appropriate URIs, such as is done in HTML forms and URI templates, by defining those instructions within media types and link relations. [Failure here implies that clients are assuming a resource structure due to out-of band information, such as a domain-specific standard, which is the data-oriented equivalent to RPC’s functional coupling].
A REST API should never have “typed” resources that are significant to the client. Specification authors may use resource types for describing server implementation behind the interface, but those types must be irrelevant and invisible to the client. The only types that are significant to a client are the current representation’s media type and standardized relation names. [ditto]
A REST API should be entered with no prior knowledge beyond the initial URI (bookmark) and set of standardized media types that are appropriate for the intended audience (i.e., expected to be understood by any client that might use the API). From that point on, all application state transitions must be driven by client selection of server-provided choices that are present in the received representations or implied by the user’s manipulation of those representations. The transitions may be determined (or limited by) the client’s knowledge of media types and resource communication mechanisms, both of which may be improved on-the-fly (e.g., code-on-demand). [Failure here implies that out-of-band information is driving interaction instead of hypertext.]


### IMPORTANT QUESTION AND FOLLOW-UP

Clarification concerning Hypertext vs. Hypermedia: when you state that the API must be hypertext-drive, you’re not implying restrictions on the representation, but properties it must exhibit, namely the ability for connecting a representation to other resources and operations thereon, correct? Then, why no say hypermedia-driven to avoid any confusion with implying that REST would be restricted to HTML?

Roy T. Fielding says:
October 20, 2008 at 7:44 am
I have a slide in my REST talk that explains what hypertext (and hypermedia) means.

Hypertext has many definitions:

Ted Nelson’s original definition was focused on non-linear documents.

By ‘hypertext,’ I mean non-sequential writing — text that branches and allows choices to the reader, best read at an interactive screen. As popularly conceived, this is a series of text chunks connected by links which offer the reader different pathways. [Theodor H. Nelson]

Later, hypertext became associated with a particular user interface mechanism.

Hypertext is a computer-supported medium for information in which many interlinked
documents are displayed with their links on a high-resolution computer screen. [Jeffrey Conklin]

When I say hypertext, I mean the simultaneous presentation of information and controls such that the information becomes the affordance through which the user (or automaton) obtains choices and selects actions. Hypermedia is just an expansion on what text means to include temporal anchors within a media stream; most researchers have dropped the distinction.

Hypertext does not need to be HTML on a browser. Machines can follow links when they understand the data format and relationship types.
