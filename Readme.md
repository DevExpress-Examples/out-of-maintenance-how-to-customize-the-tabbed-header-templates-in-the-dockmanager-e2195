<!-- default badges list -->
![](https://img.shields.io/endpoint?url=https://codecentral.devexpress.com/api/v1/VersionRange/128643404/10.2.3%2B)
[![](https://img.shields.io/badge/Open_in_DevExpress_Support_Center-FF7200?style=flat-square&logo=DevExpress&logoColor=white)](https://supportcenter.devexpress.com/ticket/details/E2195)
[![](https://img.shields.io/badge/📖_How_to_use_DevExpress_Examples-e9f6fc?style=flat-square)](https://docs.devexpress.com/GeneralInformation/403183)
<!-- default badges end -->
<!-- default file list -->
*Files to look at*:

* [DockPane.xaml](./CS/CustomTheme/DockPane.xaml) (VB: [DockPane.xaml](./VB/CustomTheme/DockPane.xaml))
* [TabbedPane.xaml](./CS/CustomTheme/TabbedPane.xaml) (VB: [TabbedPane.xaml](./VB/CustomTheme/TabbedPane.xaml))
* [Window1.xaml](./CS/CustomTheme/Window1.xaml) (VB: [Window1.xaml](./VB/CustomTheme/Window1.xaml))
* [Window1.xaml.cs](./CS/CustomTheme/Window1.xaml.cs) (VB: [Window1.xaml.vb](./VB/CustomTheme/Window1.xaml.vb))
<!-- default file list end -->
# How to customize the tabbed header templates in the DockManager


<p>It's necessary to re-specify templates corresponding to the defined resource keys. The tabbed group page header and template are placed in the TabbedPaneElementsThemeKey. The resource keys for the page header are the PageHeader and Template keys, respectively. These are the keys you should re-specify:</p>
<p> </p>


```xaml
<ControlTemplate x:Key="{dxt:TabbedPaneElementsThemeKey ResourceKey=Template}" TargetType="{x:Type ve:TabbedPane}">
<ControlTemplate x:Key="{dxt:TabbedPaneElementsThemeKey ResourceKey=PageHeader}" TargetType="{x:Type TabItem}">
```


<p> </p>
<p>To change an appearance of a tabbed header based on the panel Name property, add the following DataTrigger to the ControlTemplate.Triggers of the "{dxt:TabbedPaneElementsThemeKey ResourceKey=PageHeader}" key:</p>
<p> </p>


```xaml
<DataTrigger Binding="{Binding Path=Name}" Value="MyPanel">
    <Setter Property="Background" TargetName="inactive_border" Value="#FFD4A8BD" />
    <Setter Property="Background" TargetName="inactive" Value="#FFF5D3C3" />
</DataTrigger>

```


<p><br>In the sample, the panel with the Name property equal to MyPanel is shown using a different color than other panels.</p>

<br/>


