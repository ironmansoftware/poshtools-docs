# Custom WPF Widget

The following example creates a custom WPF widget on the desktop.

```powershell
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadWidget {
       [xml]$Form = "<Window xmlns=`"http://schemas.microsoft.com/winfx/2006/xaml/presentation`"><Grid><Label Content=`"Hello, World`" Height=`"30`" Width=`"110`"/></Grid></Window>"
       $XMLReader = (New-Object System.Xml.XmlNodeReader $Form)
       [Windows.Markup.XamlReader]::Load($XMLReader)
   } -Height 200 -Width 200 -Top 200 -Left 200
)
```
