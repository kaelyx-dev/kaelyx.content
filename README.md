# Content

Using Github as a CMS :)

## TODO:
* Landing Page, does landing page come from kaelyx.config or is it part of the site?
* Add an error state for if config or directory walker fails
    * Contact me if its borked 
* Directory Walker X
    *  Caching and cache invalidation X
* Article Parser
    *  Preparsing (Shortcodes for modules I will make) X
    *  Parsing (Marked.js?)
    *  Postparsing (Sanitization, DOMPurify, insane?)
* Move Persistance of Stores into its own module (repeated code in walker.js and config.js
* Convert relative imports to @alias imports
* Allow the stores to handle their loading state that other components can listen to.
