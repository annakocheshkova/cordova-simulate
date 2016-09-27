This directory contains tools for building JSON files for localization. The `xliff` directory
contains `xlf` files that are generated by this tool (and updated or removed as source files change),
and maintained by the loc team. 
 
Run the `update` script in this directory (`npm run update-loc`) to synchronize. It performs the
following tasks:

* Reads in any existing `xlf` files.
* Processes `html` files in the project, extracting translatable text and adding `data-loc-id`
  attributes to elements that contain translatable text (for tracking purposes). 
* Deletes `xlf` files that no longer apply (source `html` file no longer exists).
* Updates `xlf` files with new strings that need translating.
* Generates `json` files that are used to translate HTML files at runtime (under `src/i18n`).
 
 TODO items:
 * Remove `data-loc-id` attributes that are no longer needed.
 * Remove strings from `xlf` files that are no longer needed.