# Generic information on the Anycubic Photon S

| -- | -- |
| Motherboard Version | v1.9.0 |
| CPU | STM32F407ZET6 |
| FPGA | Xilinx Spartan 6 |

Possibly a Chitu rebrand.

SPI Flash from U3 is dumped into `firmware/U3-flash-W25Q16.V_1.bin`.  My
hypothesis was that, as a few of the pins were connected to the Spartan 6 FPGA,
that this would contain the bitstream for the FPGA.  An initial scan with
`binwalk` confirms that the appropriate magic numbers are present for a Xilinx
FPGA:

```bash
$ binwalk firmware/U3-flash-W25Q16.V_1.bin 

DECIMAL       HEXADECIMAL     DESCRIPTION
--------------------------------------------------------------------------------
12            0xC             Xilinx Virtex/Spartan FPGA bitstream dummy + sync word
250011        0x3D09B         LZMA compressed data, properties: 0xC0, dictionary size: 0 bytes, uncompressed size: 64 bytes
```



<!--
vim: ts=2 sw=2 et tw=80
-->
