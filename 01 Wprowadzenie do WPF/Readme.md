# Wprowadzenie do WPF

## Przydatne linki

https://learn.microsoft.com/en-us/dotnet/desktop/wpf/overview/

https://web.archive.org/web/20230319224334/http://www.wpftutorial.net/Controls.html



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

## Wbudowane w WPF kontrolki:
- Guziki (Buttons): `Button`, `RepeatButton`.
- Wyświetlanie danych (Data Display): `DataGrid`, `ListView`, `TreeView`.
- Wyświetlanie danych i wybór (Date Display and Selection): `Calendar`, `DatePicker`.
- Okna dialogowe (Dialog Boxes): `OpenFileDialog`, `PrintDialog`, `SaveFileDialog`.
- Cyfrowy kałamarz (Digital Ink): `InkCanvas`, `InkPresenter`.
- Dokumenty (Documents): `DocumentViewer`, `FlowDocumentPageViewer`, `FlowDocumentReader`, `FlowDocumentScrollViewer`, `StickyNoteControl`.
- Wprowadzanie (Input): `TextBox`, `RichTextBox`, `PasswordBox`.
- Układ (Layout): `Border`, `BulletDecorator`, `Canvas`, `DockPanel`, `Expander`, `Grid`, `GridView`, `GridSplitter`, `GroupBox`, `Panel`, `ResizeGrip`, `Separator`, `ScrollBar`, `ScrollViewer`, `StackPanel`, `Thumb`, `Viewbox`, `VirtualizingStackPanel`, `Window`, `WrapPanel`.
- Media: `Image`, `MediaElement`, `SoundPlayerAction`.
- Menus: `ContextMenu`, `Menu`, `ToolBar`.
- Navigation: `Frame`, `Hyperlink`, `Page`, `NavigationWindow`, `TabControl`.
- Wybór (Selection): `CheckBox`, `ComboBox`, `ListBox`, `RadioButton`, `Slider`.
- Informacja użytkownika (User Information): `AccessText`, `Label`, `Popup`, `ProgressBar`, `StatusBar`, `TextBlock`, `ToolTip`.