# Aligning-SixLoWPAN-according-to-RFC-
Wireless Networks course project on SixLoWPAN
## March 11 - 24
Reading RFC 4944
## UDP Compression Summary
Bits 5 and 6 of HC! encoding indicates compresion of next header(TCP,UDP,ICMP).

If bit 5 and 6 of HC1 encoding correspond to:

00 : Next header is not compressed

01 : UDP compression

10 : ICMP Compression

11 : TCP compression


Bit 7 of HC1 encoding:

1 : Indicates HC1 encoding immediately followed by more header compression

0: No more header compression bits



0 1 2 3 4 5 6 7 8 9 10 1 2 3 4 5 6 7 8 9 20 1 2 3 4 5 6 7 8 9 30 1
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
|HC_UDP encoding|  Fields carried in-line follow...
|               |
+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+-+
          UDP compressed header
