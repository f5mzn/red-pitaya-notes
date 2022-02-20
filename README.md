[![DOI](https://zenodo.org/badge/28404370.svg)](https://zenodo.org/badge/latestdoi/28404370)

# Red Pitaya Notes

Notes on the Red Pitaya Open Source Instrument

http://pavel-demin.github.io/red-pitaya-notes/

# Reason for this fork

This is a fork of the great Red Pitaya repository maintened by Pavel Demin.

I needed some specific modifications to the `sdr_transceiver_122_88` project
in order to send Band Data of each RX inputs to the gpio:

* DIO0_P to DIO3_P: band data for IN1
* DIO4_P to DIO7_P: band data for IN2

I use this setup for RX only so the code relative to the PTT outputs is
removed. It is maybe possible to have both PTT and Band Data working at once.
As a beginner, this is something I currently don't know how to it. If I get
there later, it will be an opportunity to propose a pull request instead of
this fork.

## Disclaimer

As previously stated, I am a beginner in the Red Pitaya (and more generally
FPGA) world. Please let me know if you see any errors or better ways to do it.
Thank you for your indulgence.
## Install the developement machine

See the Pavel Demin's 
[http://pavel-demin.github.io/red-pitaya-notes/development-machine/](web site).

## Open the Block Design in `Vivado`

Generate the project file on the Development Machine:

```
$ git clone https://github.com/f5mzn/red-pitaya-notes
$ cd red-pitaya-notes
$ source /opt/Xilinx/Vivado/2020.2/settings64.sh
$ make NAME=sdr_transceiver_122_88 PART=xc7z020clg400-1 xpr
```

Then open the project file `sdr_transceiver_122_88.xpr` located in
`red-pitaya-notes/sdr_transceiver_122_88.xpr`.

At first, I used it to understand how pavel designed the project,
then I was able to make the changes I wanted.
However, I still haven't managed to revert my modifications to the `tcl` files
of the project, and I had to do it manually. 

## Build the bitstream file

The `bitstream` is build on the development machine.

```
$ git clone https://github.com/f5mzn/red-pitaya-notes
$ cd red-pitaya-notes
$ source /opt/Xilinx/Vivado/2020.2/settings64.sh
$ make NAME=sdr_transceiver_122_88 PART=xc7z020clg400-1 bit
```

## Build the server

The server is build directly on the Red Pitaya, not on the Development Machine.

```
# apk add make gcc
# cd ~/apps/sdr_transceiver_122_88
# make
```
