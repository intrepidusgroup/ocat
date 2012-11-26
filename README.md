OCAT - Obj-C ARM Tools
====

Optimistically, this is a collection of tools for derping around with 
Objective-C stuff on ARM platforms (iOS binaries). Realistically, this 
"collection" currently consists of:

objc-arm-xref-parser.py

This script is designed to parse through the IDA Pro database (IDB) for an 
ARM Objective-C binary and build method-to-method cross references (xrefs).
The basic technique is to parse through the "__objc_methanme" segment, find
xrefs to every method name string that come from the "__objc_const" segment,
and read function pointers out of the "const" structures. 

This is a quick and dirty, unscientific approach. We're taking advantages of 
the heavy lifting that IDA has already accomplished for us and using it to
squeeze out some additional functionality.

CAUTION: This script has the ability to mess up your IDB file in a ways that 
you will not appreciate. Back up your IDB!