# Siemens MS41

TunerPro RT definition files (XDF) for the **Siemens MS41** engine control unit.

📖 Documentation, pinout and tuning guide: **[Siemens MS41 on the MS4X Wiki](https://www.ms4x.net/index.php?title=Siemens_MS41)**

## Definition files

| File | Language | Binary | Base offset |
|---|---|---|---|
| [`Siemens_MS41_1429861_ENG_256K_v1.0.xdf`](definitions/Siemens_MS41_1429861_ENG_256K_v1.0.xdf) | English | 256 KB full read | 0x14000 |
| [`Siemens_MS41_1429861_ENG_24K_v1.0.xdf`](definitions/Siemens_MS41_1429861_ENG_24K_v1.0.xdf) | English | 24 KB calibration | 0x0 |
| [`Siemens_MS41_1429861_GER_256K_v1.0.xdf`](definitions/Siemens_MS41_1429861_GER_256K_v1.0.xdf) | German (DAMOS names) | 256 KB full read | 0x14000 |
| [`Siemens_MS41_1429861_GER_24K_v1.0.xdf`](definitions/Siemens_MS41_1429861_GER_24K_v1.0.xdf) | German (DAMOS names) | 24 KB calibration | 0x0 |

File name scheme: `Siemens_MS41_<software>_<language>_<binary size>_<version>.xdf`

### What's inside (v1.0)

- all 670 ROM calibration values, curves and maps of software **1429861**, generated from the original DAMOS listing
- axes as separate, linked tables (`ldp_…` single-use, `ldpm_…` shared) – edit an axis once, all maps using it follow
- English version uses the Siemens English naming known from MS42/MS43 (`c_` constants, `id_`/`ip_` tables); every description starts with the original German DAMOS name
- entries sorted: axes, constants, tables without interpolation, tables with interpolation

## Usage

1. Read your DME with a [flashing tool](https://www.ms4x.net/index.php?title=Flashing_Tools) and check the software number (1429861).
2. Open the binary in [TunerPro RT](https://www.tunerpro.net) and load the XDF that matches your **binary size**.
3. Compare a few known values (e.g. rev limiter, injector scaling) before changing anything.
4. Keep an untouched backup of the original read.

<!-- TODO: note on checksum correction / which tool writes the 24K calibration -->

## Changelog

| Version | Date | Changes |
|---|---|---|
| v1.0 | 2026-09-11 | Initial release: complete DAMOS conversion, English + German, 24K + 256K |

## Contributing

Wrong conversion, unit or translation? Please [open an issue](https://github.com/ms4x-net/ms41/issues) with the table name, what you expected and your software number.

## License & disclaimer

Definition files are released under [GPL-3.0](LICENSE).

> [!WARNING]
> For off-road / closed-course use only. No warranty – you modify your ECU at your own risk.
