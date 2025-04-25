# Content

Using Github as a CMS :)

## TODO:
* Landing Page, does landing page come from kaelyx.config or is it part of the site?
* Add an error state for if config or directory walker fails
    * Contact me if its borked 
* Directory Walker
    *  Caching and cache invalidation
* Article Parser
    *  Preparsing (Shortcodes for modules I will make) X
    *  Parsing (Marked.js?)
    *  Postparsing (Sanitization, DOMPurify, insane?)
* Config Refactor
    * Local configs merged into global config store
    * Remote config takes higher precedence
    * Convert local configs into using the global config store
