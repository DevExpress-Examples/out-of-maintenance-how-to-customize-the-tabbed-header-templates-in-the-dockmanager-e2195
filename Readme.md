<!-- default file list -->
*Files to look at*:

* [DockPane.xaml](./CS/CustomTheme/DockPane.xaml) (VB: [DockPane.xaml](./VB/CustomTheme/DockPane.xaml))
* [TabbedPane.xaml](./CS/CustomTheme/TabbedPane.xaml) (VB: [TabbedPane.xaml](./VB/CustomTheme/TabbedPane.xaml))
* [Window1.xaml](./CS/CustomTheme/Window1.xaml) (VB: [Window1.xaml.vb](./VB/CustomTheme/Window1.xaml.vb))
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


