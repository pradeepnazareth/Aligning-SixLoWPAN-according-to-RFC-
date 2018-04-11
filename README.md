# Aligning 6LoWPAN according to RFC4944
## Course Code: CS821

### Overview

6LoWPAN performs compression of IPv6 Packets specified by RFC 4944 with exception of HC2 encoding.

### Description

HC2 encoding performs compression of UDP header.

Bits 5 and 6 of LOWPAN_HC1 (HC1 encoding ) encoding indicates compresion of next header(TCP/UDP/ICMP).

If bit 5 and 6 of LOWPAN_HC1 correspond to:

00 : Next header is not compressed

01 : UDP compression

10 : ICMP Compression

11 : TCP compression


Bit 7 of HC1 encoding:

1 : Indicates LOWPAN_HC1 immediately followed by more header compression

0: No more header compression bits

### UDP Compressed header encoding

UDP encoding has 8 bits correspond to:

#### UDP source port(bit 0):
0: Not compressed
1: compressed to 4 bits from 16 bits.
Source Port= P + short_port value.
where P= 0xF0B0 (decimal 61616).
short_port value expressed as a 4-bit value carried-in-line.

#### UDP destination port(bit 1):
0: Not Compressed

1: Compressed to 4 bits from 16 bits.

Destination Port= P + short_port value.

where P= 0xF0B0 (decimal 61616).
short_port value expressed as a 4-bit value carried "in-line".

#### Length (bit 2):
0 : Not compressed
1:  Compressed. The UDP length field is equal to payload lenth from IPv6 header - length of any headers present between IPv6 header and UDP header

#### Reserved (bit 3 through 7)

#### References:
1. RFC 4944

2.http://cnds.eecs.jacobs-university.de/slides/2010-aims-6lowpan.pdf

3.http://www.cse.wustl.edu/~jain/cse570-13/ftp/m_19lpn.pdf



