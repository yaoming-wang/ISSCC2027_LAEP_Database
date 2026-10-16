# ISSCC2027_LAEP_Database
This dataset contains the measured efficiency results of a phase-scalable Linked Equal-charge-transfer Alternating-polarity Path (LEAP) hybrid converter developed for an ISSCC 2027 submission. 
# LEAP hybrid converter efficiency measurement data

This dataset contains measured efficiency results for a phase-scalable Linked Equal-charge-transfer Alternating-polarity Path (LEAP) hybrid converter developed for an ISSCC 2027 submission. The measurements cover a nominal 12-V input, regulated outputs of 1 V and 1.8 V, and 2-, 4-, and 6-phase operation. Each record reports the output current and voltage, input voltage and current, and calculated power-conversion efficiency.

## Files

The archive contains two Excel workbooks:

- `12V_1V.xlsx`: efficiency measurements at a 1-V output.
- `12V_1.8V.xlsx`: efficiency measurements at a 1.8-V output.

Each workbook contains one worksheet divided into three side-by-side sections. From left to right, the sections contain the 6-phase, 4-phase, and 2-phase measurements. Blank columns separate the sections.

## Workbook organization

The first row of each section identifies the active phase count and the corresponding `P_DRV` value. The second row contains the data headers, followed by the measurement points.

| Field | Description | Unit |
| --- | --- | --- |
| `IO` | Converter output current | A |
| `VO` | Converter output voltage used in the efficiency calculation | V |
| `VIN` | Measured converter input voltage | V |
| `IIN` | Measured converter input current | A |
| `P_DRV` | Fixed power term representing gate-driver and related auxiliary losses for the active phase configuration | W |
| `EFF` | Power-conversion efficiency expressed as a decimal fraction | unitless |

For example, an `EFF` value of `0.908` corresponds to an efficiency of 90.8%.

## Efficiency calculation

Efficiency is calculated separately for each measurement point as:

```text
EFF = (VO × IO) / (VIN × IIN + P_DRV)
```

Thus, `P_DRV` is included in the total input power. The fixed values used for the three operating configurations are:

| Active phases | `P_DRV` |
| --- | ---: |
| 6 phases | 0.033 W |
| 4 phases | 0.022 W |
| 2 phases | 0.011 W |


## Measurement conditions

- Nominal input voltage: 12 V.
- Output-current increment: 0.2 A.
- Continuous-load testing at room temperature without external cooling.
- Settling time: more than 30 s at each measurement point.

The dataset can be used to reproduce the reported efficiency curves and evaluate efficiency trends versus output current, output voltage, and active phase count.
