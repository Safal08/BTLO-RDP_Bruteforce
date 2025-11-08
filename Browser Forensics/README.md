**Author:** Safal

**Date:** 2025-11-08

**Tools:** FTK Imager

Analysis of Browser forensic from FTK Imager

Challenge URL: https://blueteamlabs.online/home/challenge/browser-forensics-cryptominer-aa00f593cb

Tool Download Link : https://www.exterro.com/ftk-product-downloads/ftk-imager-4-7-3-81

**Incident Summary**

**Extension Analysis:**

Navigated to the path:
Default\Extensions\

Each folder name corresponds to a Chrome Extension ID.

Noted the following example entry:

Extension ID: egnfmleidkolminhjlkaomjefheafbbb

Manifest File: manifest.json

Provided details about the extension name, version, permissions, and author.

**JavaScript File Examination:**

Several .js files within the extension directory were examined for suspicious code.

One JavaScript file contained obfuscated code referencing functions such as CryptoJS, WebAssembly, and repeated network requests to external mining pools.

Indicators suggested the presence of a cryptominer script (e.g., browser-based mining of Monero using WebAssembly).

**Takeways**

1. Learned how to use FTK Imager to explore and extract data from a forensic image (.ad1).
2. Gained experience identifying Chrome themes and extension IDs from browser data.
3. Improved skills in analyzing JavaScript files for signs of malicious or cryptomining activity.
4. Understood the importance of browser forensics in detecting hidden threats.
