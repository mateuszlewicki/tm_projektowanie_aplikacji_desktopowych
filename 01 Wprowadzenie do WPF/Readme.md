# Wprowadzenie do WPF

## Przydatne linki

https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/





## Co to jest WPF?
Windows Presentation Foundation (WPF), to framework UI, który jest niezależny od rozdzielczości i używa silnika renderującego opartego na wectorach. WPF wyjorzystuje directx do renderowania. WPF dostarcza kompleksowego zestawu możliwości do tworzenie aplikacji okienkowych takich jak XAML - Extensible Application Markup Language, kontrolki, data binding, layout, grafika 2D i 3D , animacje, style, template'y, dokumenty, media, tekst, i typografia. WPF jest częścią platformy .NET.

## Znaczniki i kod
WPF pozwana na tworzenie aplikacji z wykorzystaniem kodu i znaczników. Zachowuje się zwyczajowo taki podział - XAML używany do tworzenia części wizualnej aplikacji natomiast logikę piszemy za pomocą języka C# (lub VB)

```xml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    Title="Window with button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button">Click Me!</Button>

</Window>
```

![image](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/media/index/markup-window-button.png)

```xml
<Window
    xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation"
    xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml"
    x:Class="SDKSample.AWindow"
    Title="Window with button"
    Width="250" Height="100">

  <!-- Add button to window -->
  <Button Name="button" Click="button_Click">Click Me!</Button>

</Window>
```


```cs
using System.Windows;

namespace SDKSample
{
    public partial class AWindow : Window
    {
        public AWindow()
        {
            // InitializeComponent call is required to merge the UI
            // that is defined in markup with this class, including  
            // setting properties and registering event handlers
            InitializeComponent();
        }

        void button_Click(object sender, RoutedEventArgs e)
        {
            // Show message box when button is clicked.
            MessageBox.Show("Hello, Windows Presentation Foundation!");
        }
    }
}
```

![image](https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/media/index/markup-window-button-clicked.png)