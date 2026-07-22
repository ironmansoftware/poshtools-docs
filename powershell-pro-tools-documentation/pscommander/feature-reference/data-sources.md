# Data Sources

Data sources allow you to load data a single time and use it with multiple desktop widgets. This provides better performance than loading the data in each widget. It also provides data binding support for WPF components.

To register a data source, use the `Register-CommanderDataSource` cmdlet. The following data source loads computer performance information every 5 seconds.

```powershell
Register-CommanderDataSource -Name 'ComputerInfo' -LoadData {
   $Stats = Get-NetAdapterStatistics
   $NetworkDown = 0
   $Stats.ReceivedBytes | Foreach-Object { $NetworkDown += $_ }

   $NetworkUp = 0
   $Stats.SentBytes | Foreach-Object { $NetworkUp += $_ }

   @{
       CPU = Get-CimInstance Win32_Processor | Measure-Object -Property LoadPercentage -Average | Select-Object -Expand Average
       Memory = (Get-Counter '\Memory\Available MBytes').CounterSamples.CookedValue
       NetworkUp = $NetworkUp / 1KB
       NetworkDown = $NetworkDown / 1KB
   }
} -RefreshInterval 5
```

To use this data source with a desktop widget, use the `-DataSource` parameter for a custom widget. Every time the data source is updated, the WPF custom widget is notified and loads UI components.

This example creates a small, grey bar that formats and displays the computer information.

```powershell
New-CommanderDesktop -Widget @(
   New-CommanderDesktopWidget -LoadWidget {
       [xml]$Form = Get-Content C:\Users\adamr\Desktop\test.xaml -Raw
       $XMLReader = (New-Object System.Xml.XmlNodeReader $Form)
       [Windows.Markup.XamlReader]::Load($XMLReader)
   } -Height 200 -Width 1400 -Top 20 -Left 100 -DataSource 'ComputerInfo'
}
```

The XAML can take advantage of binding to the hashtable created by the data source.

```xml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    WindowStyle="None"
    ResizeMode="NoResize"
    Background="Transparent"
    Height="200"
    Width="1900"
>
    <Grid Margin="10">
        <Border BorderBrush="#333333" BorderThickness="1" Background="#333333" Grid.Column="1"
                CornerRadius="10" VerticalAlignment="Center"
                HorizontalAlignment="Stretch">
            <Grid Margin="10">

                <Grid.ColumnDefinitions>
                    <ColumnDefinition Width="200"/>
                    <ColumnDefinition Width="200"/>
                    <ColumnDefinition Width="300"/>
                    <ColumnDefinition Width="300"/>
                </Grid.ColumnDefinitions>

                <Grid.RowDefinitions>
                    <RowDefinition />
                    <RowDefinition Height="Auto" />
                </Grid.RowDefinitions>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding CPU, StringFormat=CPU: {0}%}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="0"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding Memory, StringFormat=Available Memory: {0:N0} MB}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="1"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding NetworkUp, StringFormat=Network Up: {0:N0} KB\s}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="2"/>
                <TextBlock DataContext="{Binding CurrentValue}" Text="{Binding NetworkDown, StringFormat=Network Down: {0:N0} KB\s}" TextWrapping="Wrap" Margin="5" Foreground="#28bf37" FontFamily="Consolas" Grid.Column="3"/>
            </Grid>
        </Border>
    </Grid>
</Window>
```

This produces a widget that looks like this.

![](<../../../.gitbook/assets/image (64).png>)
