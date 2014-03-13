sa-normalize
============

SpamAssassin Tool for previewing ASCI and UTF8 normalizing for rules development


Description
-----------
This is a simple utility for converting text in diverse languages and diverse
character sets either to UTF-8, or to plain 7bit US-ASCII. In the second case
discritics is stripped off from Latin characters, and non-Latin letters, 
including sign alphabets, are transcribed to non-accented Latin characters.

The tool was written for testing purposes, to simulate the result of "norma-
lizing" done by SpamAssassin. UTF8 normalizing can be turned on in SpamAssassin
by setting normalize_charset to 1. A patch for US-ASCII normalizing was recently 
published on the Dev mailing list.

The text can be fed to the tool either directly on the command line, or in a file.
Please note that the tool currently does not parse any email messages. It requires
plain text in one of many available character sets. No base64, quoted-printable,
or othersimilar encoding is currently parsed. Only HTML entities are converted.

The script attempts to detect the character set of the souce text automatically,
but when there is not sufficient data, it may fail, and fall back to the default 
UTF-8. In such case you can force the desired charset by the switch -in.


Installation
------------
No installation is needed, you only need recent functional Perl, SpamAssassin,
and some more or less standard Perl modules. One of the less standard ones, that
may require a separate installtion is the Text::Unidecode module, which can be 
found among Perl convertors in most Unix distributions.

The package contains also some sample texts in several languages and several
character sets, for testing.


Examples of use
---------------

Usage help:   
> ./sa-normalize -h 

Changelog:    
> ./sa-normalize -changelog

> ./sa-normalize "Tschüß böse Mädchen!"
> ./sa-normalize -q -out UTF8 "Έλληνες"
> ./sa-normalize japanese-utf8.txt


Author
------
Ivo Truxa <truxa@truxoft.com>
 - v1.00 published on 13th March, 2014


License
-------
Apache License 2.0
