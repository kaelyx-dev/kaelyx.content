# Content

Using Github as a CMS :)

## TODO:
* Content
    * Landing Page, does landing page come from kaelyx.content or is it part of the site?
    * Overflow scrolling on content, fixing content box size.
    * Fixing md->html content such as UL/OL/LI etc.
    * Content 404 if the permalink or site link could not be found
* Components
    * Directory Walker (DONE)
        * Caching and cache invalidation (DONE)
    * Content Parser
        *  Preparsing (Pulling out content metadata) (HALF DONE) --> FORMALISE AVAILABLE META KEYS AVAILABLE
        *  Parsing (Marked.js?) (DONE)
        *  Postparsing (Sanitization, DOMPurify?) (DONE)
* Modules
    * Persistance
        *  Move persistance of stores into its own module
            * setPersistance and getPersistance.
    * Permalink (DONE)
        * Base62 or Sanitized B64 ie: URIEncode before sending (DONE) --> B64 then URIEncode

* Error Handling
    * Handling if conf or page stores fail to load
    * Add an error state for if config or directory walker fails
        * Contact me if its borked

* Housekeeping
    * Convert relative imports to @alias imports

* Head
    * Head component for canonical tag, meta description tag etc.
    *
## Proposed Features:
* Postit component
* Fontawesome or related icon support (add a shortcode too)
* Banner component, using conf values maybe, motd.conf? pick from a random list etc.
* Cookie Banner (Possible GTM / GA4 Integration)?? Probably not, very down the line.
* Image Dialog Component
* Script Loader -> Put in head or foot
