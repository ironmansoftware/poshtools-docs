# Image Widget

The following example creates an image widget on the desktop.

```powershell
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -Image 'C:\src\blog\content\images\news.png' -Height 200 -Width 200 -Top 200
)
```
