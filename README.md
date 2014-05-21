jquery-i18n-properties
======================

# About

jQuery-i18n-properties is a lightweight jQuery plugin for providing internationalization to javascript from ‘.properties’ files, just like in Java Resource Bundles. It loads and parses resource bundles (.properties) based on provided language and country codes (ISO-639 and ISO-3166) or language reported by browser.

Resource bundles are ‘.properties‘ files containing locale specific key-value pairs. The use of ‘.properties‘ files for translation is specially useful when sharing i18n files between Java and Javascript projects. This plugin loads the default file (eg, Messages.properties) first and then locale specific files (Messages_pt.properties, then Messages_pt_PT.properties), so that a default value is always available when there is no translation provided. Translation keys will be available to developer as javascript variables/functions (functions, if translated value contains substitutions (eg, {0}) or as a map.

Various enhancements and testing has been added to it to support language priority with fallback, accept-header format and default language support.

This is a fork of jquery-i18n-properties located here: https://code.google.com/p/jquery-i18n-properties/, and is made available under a dual license (GPL and MIT).


# Features
* Use Java standard ‘.properties‘ files for translations
* Use standard ISO-639 for language code and ISO-3166 for country code
* Sequential loading of resource bundles from base language to user-specified/browser-specified so there is always a default value for an untranslated string (eg: msg.properties, msg_pt.properties, msg_pt_PT.properties)
* Accept-header language support
* Cache busting support based on customizable parameter (e.g. your product build version)
* Use browser reported language if no language was specified
* Placeholder substitution in resource bundle strings (eg, msg_hello = Hello {0}!!)
* Suport for namespaces in keys (eg, com.company.msgs.hello = Hello!)
* Support for multi-line property values
* Language priority with fallback including a default bundle
** e.g. If the user wants japanese, korean then english, the key lookup will check the japanese strings then korean then english until a match is found
* Support for country and region
** e.g. en_UK will take priority then fall back to en

#Added Feature in fork
*The callback method gets a variable back with
    *foundLocaleSpecificFile: true if found false otherwise
