# FT232H breakout board OpenOCD config

## tl;dr?

- Pinout:
  <table>
    <tr>
      <th>Pin</th>
      <th>JTAG</th>
      <th>SWD</th>
    </tr>
    <tr>
      <td>D0</td>
      <td>TCK</td>
      <td>CLK</td>
    </tr>
    <tr>
      <td>D1</td>
      <td>TDI</td>
      <td>DIO</td>
    </tr>
    <tr>
      <td>D2</td>
      <td>TDO</td>
      <td>DIO</td>
    </tr>
    <tr>
      <td>D3</td>
      <td>TMS</td>
      <td></td>
    </tr>
    <tr>
      <td>D4</td>
      <td colspan=2 align=center>nTRST</td>
    </tr>
    <tr>
      <td>D5</td>
      <td colspan=2 align=center>nSRST</td>
    </tr>
  </table>

- Scroll to the bottom of the config to set JTAG/SWD

## What is this?

This repo holds a configuration for using the FTDI FT232H (as an adapter) with
[OpenOCD](https://openocd.org/). There are few other examples out there, I've
found these to be either vendor-specific, with errors, and/or with little
explanation of the configuration. As OpenOCD's docs can be a bit heavy for the
novice, this config aims to explain why its parameters are set as they are.

The FT232H is an inexpensive entrypoint into hardware debugging and hacking. The
chips come with sane defaults, but can be further configured using FTDI's
[FT_PROG (Windows Only)](https://ftdichip.com/utilities/#ft_prog) software if
necessary.

## References

- [FTDI FT232H datasheet](https://ftdichip.com/wp-content/uploads/2023/09/DS_FT232H.pdf)
- [OpenOCD `ftdi` driver source](https://sourceforge.net/p/openocd/code/ci/9623069e8090fbbf80250836e82feaecdb65233e/tree/src/jtag/drivers/ftdi.c)
- [OpenOCD docs on adapter config](https://openocd.org/doc/html/Debug-Adapter-Configuration.html)
- [Intel docs on JTAG pull-ups/downs](https://www.intel.com/content/www/us/en/docs/programmable/683546/current/pull-up-and-pull-down-of-jtag-pins-during.html)
