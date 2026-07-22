# Measurement Widget

The following creates a measurement widget on the desktop.

```powershell
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadMeasurement {Get-Random} -MeasurementTitle 'Random' -MeasurementSubtitle 'A random number' -MeasurementUnit 'units' -Height 300 -Width 500 -Left 600 -Top 200 -MeasurementFrequency 1 -MeasurementDescription "Nice" -MeasurementTheme 'DarkBlue'
)
```
