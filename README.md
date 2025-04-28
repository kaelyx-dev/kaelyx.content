# Content

Using Github as a CMS :)

## TODO:
* Content
    * Landing Page, does landing page come from kaelyx.content or is it part of the site? 
* Components
    * Directory Walker (DONE)
        * Caching and cache invalidation (DONE)
    * Content Parser
        *  Preparsing (Pulling out content metadata)
        *  Parsing (Marked.js?)
        *  Postparsing (Sanitization, DOMPurify?)
* Modules
    * Persistance
        *  Move persistance of stores into its own module
            * setPersistance and getPersistance.  
    * Permalink (ALMOST DONE)
        * Base62 or Sanitized B64 ie: URIEncode before sending
* Error Handling
    * Handling if conf or page stores fail to load 
    * Add an error state for if config or directory walker fails
        * Contact me if its borked
     
* Housekeeping
    * Convert relative imports to @alias imports

## Proposed Features:
* Postit component
* Fontawesome or related icon support (add a shortcode too)
