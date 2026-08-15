# Webpage Widget

The following example creates a webpage widget on the desktop.

```powershell
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Url 'https://www.google.com' -Height 500 -Width 500 -Top 400
)
```
