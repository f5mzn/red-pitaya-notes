[![DOI](https://zenodo.org/badge/28404370.svg)](https://zenodo.org/badge/latestdoi/28404370)

# Red Pitaya Notes

Notes on the Red Pitaya Open Source Instrument

http://pavel-demin.github.io/red-pitaya-notes/

# Fork

This is a fork of the great Red Pitaya repository maintened by Pavel Demin.
The SDR Red Pitaya STEMlab 122.88-16 transceiver is modified in order to send the band data
of each RX inputs to the gpio:

* DIO0_P to DIO3_P: band data for IN1
* DIO4_P to DIO7_P: band data for IN2

I use this setup for RX only so the PTT outputs are removed.
