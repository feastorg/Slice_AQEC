# Docs

## parts dump

- BNC
  - same as pH
- TPS60400DBVR
  - same as pH and OR
- CD4060BM
  - https://www.digikey.ca/en/products/detail/texas-instruments/CD4060BM/1691231
- TL074HIDR
  - https://www.digikey.ca/en/products/detail/texas-instruments/TL074HIDR/13563033
- 1N4148WX-TP for FW rectifier
  - https://www.digikey.ca/en/products/detail/mcc-micro-commercial-components/1N4148WX-TP/717197

## EC range

- 0-25 mS/cm for each K setting (JP1/JP2), with a probe whose cell constant matches it,
  on the TL074H at +/-5 V.
- EC_IN (A0) is linear up to about 4.2 V. Firmware should treat EC_IN above about 4.2 V
  as over-range.
- Why: U2C's output sits a diode drop beyond the signal (-(TIA_OUT + Vf)), so it reaches
  the TL074H's output swing limit on the -5 V rail first, and EC_IN stops tracking.

## references

- DF Robot EC meter sensor
  - https://web.archive.org/web/20240221180149/https://image.dfrobot.com/image/data/DFR0300/DFR0300_v1.0_schematic.pdf
  - https://github.com/DFRobot/DFRobot_EC/blob/master/%5BDFR0300%5D(V2.0)%20Layout.pdf
  - https://www.dfrobot.com/product-1123.html
