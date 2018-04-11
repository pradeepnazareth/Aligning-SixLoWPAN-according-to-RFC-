# Aligning 6LoWPAN according to RFC4944
## Course Code: CS821

### Overview

6LoWPAN performs compression of IPv6 Packets specified by RFC 4944 with exception of HC2 encoding.

### Description

HC2 encoding performs compression of UDP header.

Bits 5 and 6 of LOWPAN_HC1 (HC1 encoding ) encoding indicates compresion of next header(TCP,UDP,ICMP).

If bit 5 and 6 of LOWPAN_HC1 correspond to:

00 : Next header is not compressed

01 : UDP compression

10 : ICMP Compression

11 : TCP compression


Bit 7 of HC1 encoding:

1 : Indicates LOWPAN_HC1 immediately followed by more header compression

0: No more header compression bits

### UDP Compressed header encoding

#### UDP source port(bit 0):
0: Not compressed
1: compressed to 4 bits from 16 bits.
