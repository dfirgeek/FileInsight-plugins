FileInsight-plugins: plugins for McAfee FileInsight hex editor

These plugins would be useful for various kind of decoding tasks in malware analysis
(e.g. extracing malware executables and decoy documents from malicious document files).

How to install:
Please copy plugin folders into %USERPROFILE%\Documents\FileInsight\plugins .
You need Python 2.7 (x86) installed in addition to FileInsight.

*** NOTE ***
Python 2.7.11 causes FileInsight to crash. Please use 2.7.12 or higher version.

Requisites:
For the "aPLib compress" and "aPLib decompress" plugins, they require aplib.dll.
Please download aPLib from http://ibsensoftware.com/download.html and copy
aplib.dll (32 bits version) into "Compression operations" folder.

For the "ARC4 decrypt" plugin, it requires PyCrypto Python module.
Please get it from http://www.voidspace.org.uk/python/modules.shtml#pycrypto
or execute "c:\Python27\python.exe -m pip install pycrypto" .

For the File type plugin, it requires python-magic Python module.
Please get it from https://github.com/ahupp/python-magic
or execute "c:\Python27\python.exe -m pip install python-magic-bin" .

For the Find PE file plugin, it requires pefile Python module.
Please get it from https://code.google.com/p/pefile/
or execute "c:\Python27\python.exe -m pip install pefile" .

You can install all required Python modules with the following command.
c:\Python27\python.exe -m pip install -r requirements.txt

Customization:
For the "Send to" plugin, please edit "Misc operations\send_to.py" to run your
favorite programs.

List of plugins (38 plugins):
* Basic operations
  * Copy to new file
    Copy selected region (the whole file if not selected) to new file
  * Delete before
    Delete all region before current cursor position
  * Delete after
    Delete all region after current cursor position
  * Fill
    Fill selected region with specified hex pattern
  * Invert
    Invert bits of selected region
  * Reverse order
    Reverse order of selected region
  * Swap nibbles
    Swap each pair of nibbles of selected region
  * Swap two bytes
    Swap each pair of bytes of selected region

* Compression operations
  * aPLib compress
    Compress selected region with aPLib compression library
  * aPLib decompress
    Decompress selected region with aPLib compression library
  * Bzip2 compress
    Compress selected region with bzip2 algorithm
  * Bzip2 decompress
    Decompress selected region with bzip2 algorithm
  * Gzip compress
    Compress selected region with gzip format
  * Gzip decompress
    Decompress selected gzip compressed region
  * LZNT1 compress
    Compress selected region with LZNT1 algorithm
  * LZNT1 decompress
    Decompress selected region with LZNT1 algorithm
  * Raw deflate
    Compress selected region with Deflate algorithm without header and checksum
    (Equivalent to gzdeflate() in PHP language)
  * Raw inflate
    Decompress selected Deflate compressed region that does not have header and
    checksum (Equivalent to gzinflate() in PHP language)

* Crypto operations
  * ARC4 decrypt
    Decrypt selected region with ARC4 (Alleged RC4)

* Encoding operations
  * Binary to hex text
    Convert binary of selected region into hex text
  * Hex text to binary
    Convert hex text of selected region into binary
  * Custom base64 decode
    Decode selected region with custom base64 table
  * Custom base64 encode
    Encode selected region with custom base64 table
  * ROT13
    Decode selected region with ROT13 algorithm

* Misc operations
  * Byte frequency
    Show byte frequency of selected region (the whole file if not selected)
  * File type
    Identify file type of selected region (the whole file if not selected)
  * Hash values
    Calculate MD5, SHA1, SHA256 hash values of selected region (the whole
    file if not selected)
  * Send to
    Send selected region (the whole file if not selected) to other programs

* Search operations
  * Find PE file
    Find PE file from selected region (the whole file if not selected)  
  * XOR hex search
    Search XORed / bit-rotated data in selected region (the whole file
    if not selected)
  * XOR text search
    Search XORed / bit-rotated string in selected region (the whole file
    if not selected)

* XOR operations
  * Decremental XOR
    XOR selected region while decrementing XOR key
  * Incremental XOR
    XOR selected region while incrementing XOR key
  * Null-preserving XOR
    XOR selected region while skipping null bytes and XOR key itself
  * XOR with next byte
    XOR selected region while using next byte as XOR key
  * Guess 256 byte XOR keys
    Guess 256 byte XOR keys from selected region (the whole file if not selected)
    based on the byte frequency
  * Visual encrypt
    Encode selected region with visual encrypt algorithm that is used by Zeus trojan
  * Visual decrypt
    Decode selected region with visual decrypt algorithm that is used by Zeus trojan

Author: Nobutaka Mantani (Email: nobutaka@nobutaka.org, Twitter: nmantani)
License: The BSD 2-Clause License (http://opensource.org/licenses/bsd-license.php)
