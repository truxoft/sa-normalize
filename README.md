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
or other similar encoding is currently parsed. Only HTML entities are converted.
