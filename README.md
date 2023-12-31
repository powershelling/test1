

Add-Type -Name Window -Namespace Console -MemberDefinition '
[DllImport("Kernel32.dll")]
public static extern IntPtr GetConsoleWindow();

[DllImport("user32.dll")]
public static extern bool ShowWindow(IntPtr hWnd, Int32 nCmdShow);'

[Console.Window]::ShowWindow([Console.Window]::GetConsoleWindow(), 0)

#-------------------------------------------------------------#
#----Initial Declarations-------------------------------------#
#-------------------------------------------------------------#

Add-Type -AssemblyName PresentationCore, PresentationFramework

$Xaml = @"
<Window xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" Width="1080" Height="576" HorizontalAlignment="Left" VerticalAlignment="Top" Margin="0,0,0,0"><Window.Resources>
	<ResourceDictionary>
		<ResourceDictionary.MergedDictionaries>
			<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d">
				<ResourceDictionary.MergedDictionaries>
					<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" xmlns:System="clr-namespace:System;assembly=mscorlib" mc:Ignorable="d">
						<ResourceDictionary.MergedDictionaries>
							<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d">
								<SolidColorBrush x:Key="Brush01" Color="#FF00AADE"/>
								<SolidColorBrush x:Key="Brush02" Color="White"/>
								<SolidColorBrush x:Key="Brush03" Color="#FFC6C6C6"/>
								<SolidColorBrush x:Key="Brush04" Color="#FF565656"/>
								<SolidColorBrush x:Key="Brush05" Color="#FF333333"/>
								<Color x:Key="Color_000">#FF282828</Color>
								<Color x:Key="Color_001">#FF3F3F3F</Color>
								<Color x:Key="Color_002">#FF565656</Color>
								<Color x:Key="Color_003">#FF858585</Color>
								<Color x:Key="Color_004">#FFB9B9B9</Color>
								<Color x:Key="Color_005">#FFD7D7D7</Color>
								<Color x:Key="Color_006">#FFE7E7E7</Color>
								<Color x:Key="Color_007">#FFF4F4F4</Color>
								<Color x:Key="Color_008">#FFF9F9F9</Color>
								<Color x:Key="Color_009">#FFFFFFFF</Color>
								<Color x:Key="Color_010">#E5FFFFFF</Color>
								<Color x:Key="Color_011">#BFFFFFFF</Color>
								<Color x:Key="Color_012">#99FFFFFF</Color>
								<Color x:Key="Color_013">#72FFFFFF</Color>
								<Color x:Key="Color_014">#4CFFFFFF</Color>
								<Color x:Key="Color_016">#00FFFFFF</Color>
								<Color x:Key="Color_018">#72000000</Color>
								<Color x:Key="Color_019">#4C000000</Color>
								<Color x:Key="Color_020">#26000000</Color>
								<Color x:Key="Color_021">#00000000</Color>
								<Color x:Key="Color_022">#66E2E2E2</Color>
								<Color x:Key="Color_023">#FF0086AF</Color>
								<Color x:Key="Color_024">#FF00AADE</Color>
								<Color x:Key="Color_025">#FF80D5EF</Color>
								<Color x:Key="Color_026">#FFB2E1EF</Color>
								<Color x:Key="Color_027">#2600AADE</Color>
								<Color x:Key="Color_028">#FFD0284C</Color>
								<Color x:Key="Color_029">#FFF55E7F</Color>
								<Color x:Key="Color_030">#FFFFCAD5</Color>
								<Color x:Key="Color_035">#FF006481</Color>
								<Color x:Key="Color_037">#FF8A9B0F</Color>
								<Color x:Key="Color_038">#FF3E4700</Color>
								<Color x:Key="Color_040">#FFF14D0F</Color>
								<Color x:Key="Color_041">#FF8D2E00</Color>
								<Color x:Key="Color_043">#FF81106B</Color>
								<Color x:Key="Color_044">#FF410135</Color>
								<Color x:Key="Color_046">#FFFCA910</Color>
								<Color x:Key="Color_047">#FF8D4902</Color>
								<Color x:Key="Color_049">#FF037A54</Color>
								<Color x:Key="Color_050">#FF003F2A</Color>
								<Color x:Key="Color_052">#FF154D85</Color>
								<Color x:Key="Color_053">#FF02284D</Color>
								<Color x:Key="Color_055">#FF543511</Color>
								<Color x:Key="Color_056">#FF211303</Color>
								<Color x:Key="Color_058">#FF89806D</Color>
								<Color x:Key="Color_059">#FF393225</Color>
								<Color x:Key="Color_061">#FF58458B</Color>
								<Color x:Key="Color_062">#FF211347</Color>
								<Color x:Key="Color_063">#7FB9B9B9</Color>
								<Color x:Key="Color_064">#33565656</Color>
								<Color x:Key="Color_065">#7F3F3F3F</Color>
								<Color x:Key="Color_066">#FF686868</Color>
								<Color x:Key="Color_067">#8000AADE</Color>
								<Color x:Key="Color_068">#CC3F3F3F</Color>
								<Color x:Key="Color_069">#FF0092BE</Color>
								<Color x:Key="Color_070">#FF00AADE</Color>
								<Color x:Key="Color_071">#FF2BB9E5</Color>
								<Color x:Key="Color_072">#FF55C8EB</Color>
								<Color x:Key="Color_073">#FF80D7F2</Color>
							</ResourceDictionary>
							<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" xmlns:System="clr-namespace:System;assembly=mscorlib" mc:Ignorable="d">
								<ResourceDictionary.MergedDictionaries>
									<ResourceDictionary xmlns="http://schemas.microsoft.com/winfx/2006/xaml/presentation" xmlns:x="http://schemas.microsoft.com/winfx/2006/xaml" xmlns:d="http://schemas.microsoft.com/expression/blend/2008" xmlns:mc="http://schemas.openxmlformats.org/markup-compatibility/2006" mc:Ignorable="d">
										<SolidColorBrush x:Key="Brush01" Color="#FF00AADE"/>
										<SolidColorBrush x:Key="Brush02" Color="White"/>
										<SolidColorBrush x:Key="Brush03" Color="#FFC6C6C6"/>
										<SolidColorBrush x:Key="Brush04" Color="#FF565656"/>
										<SolidColorBrush x:Key="Brush05" Color="#FF333333"/>
										<Color x:Key="Color_000">#FF282828</Color>
										<Color x:Key="Color_001">#FF3F3F3F</Color>
										<Color x:Key="Color_002">#FF565656</Color>
										<Color x:Key="Color_003">#FF858585</Color>
										<Color x:Key="Color_004">#FFB9B9B9</Color>
										<Color x:Key="Color_005">#FFD7D7D7</Color>
										<Color x:Key="Color_006">#FFE7E7E7</Color>
										<Color x:Key="Color_007">#FFF4F4F4</Color>
										<Color x:Key="Color_008">#FFF9F9F9</Color>
										<Color x:Key="Color_009">#FFFFFFFF</Color>
										<Color x:Key="Color_010">#E5FFFFFF</Color>
										<Color x:Key="Color_011">#BFFFFFFF</Color>
										<Color x:Key="Color_012">#99FFFFFF</Color>
										<Color x:Key="Color_013">#72FFFFFF</Color>
										<Color x:Key="Color_014">#4CFFFFFF</Color>
										<Color x:Key="Color_016">#00FFFFFF</Color>
										<Color x:Key="Color_018">#72000000</Color>
										<Color x:Key="Color_019">#4C000000</Color>
										<Color x:Key="Color_020">#26000000</Color>
										<Color x:Key="Color_021">#00000000</Color>
										<Color x:Key="Color_022">#66E2E2E2</Color>
										<Color x:Key="Color_023">#FF0086AF</Color>
										<Color x:Key="Color_024">#FF00AADE</Color>
										<Color x:Key="Color_025">#FF80D5EF</Color>
										<Color x:Key="Color_026">#FFB2E1EF</Color>
										<Color x:Key="Color_027">#2600AADE</Color>
										<Color x:Key="Color_028">#FFD0284C</Color>
										<Color x:Key="Color_029">#FFF55E7F</Color>
										<Color x:Key="Color_030">#FFFFCAD5</Color>
										<Color x:Key="Color_035">#FF006481</Color>
										<Color x:Key="Color_037">#FF8A9B0F</Color>
										<Color x:Key="Color_038">#FF3E4700</Color>
										<Color x:Key="Color_040">#FFF14D0F</Color>
										<Color x:Key="Color_041">#FF8D2E00</Color>
										<Color x:Key="Color_043">#FF81106B</Color>
										<Color x:Key="Color_044">#FF410135</Color>
										<Color x:Key="Color_046">#FFFCA910</Color>
										<Color x:Key="Color_047">#FF8D4902</Color>
										<Color x:Key="Color_049">#FF037A54</Color>
										<Color x:Key="Color_050">#FF003F2A</Color>
										<Color x:Key="Color_052">#FF154D85</Color>
										<Color x:Key="Color_053">#FF02284D</Color>
										<Color x:Key="Color_055">#FF543511</Color>
										<Color x:Key="Color_056">#FF211303</Color>
										<Color x:Key="Color_058">#FF89806D</Color>
										<Color x:Key="Color_059">#FF393225</Color>
										<Color x:Key="Color_061">#FF58458B</Color>
										<Color x:Key="Color_062">#FF211347</Color>
										<Color x:Key="Color_063">#7FB9B9B9</Color>
										<Color x:Key="Color_064">#33565656</Color>
										<Color x:Key="Color_065">#7F3F3F3F</Color>
										<Color x:Key="Color_066">#FF686868</Color>
										<Color x:Key="Color_067">#8000AADE</Color>
										<Color x:Key="Color_068">#CC3F3F3F</Color>
										<Color x:Key="Color_069">#FF0092BE</Color>
										<Color x:Key="Color_070">#FF00AADE</Color>
										<Color x:Key="Color_071">#FF2BB9E5</Color>
										<Color x:Key="Color_072">#FF55C8EB</Color>
										<Color x:Key="Color_073">#FF80D7F2</Color>
									</ResourceDictionary>
								</ResourceDictionary.MergedDictionaries>
								<SolidColorBrush x:Key="ForegroundBrush" Color="{StaticResource Color_001}" />
								<SolidColorBrush x:Key="LightForegroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="TransparentBrush" Color="{StaticResource Color_016}" />
								<SolidColorBrush x:Key="DisabledVisualElement" Color="{StaticResource Color_012}" />
								<SolidColorBrush x:Key="ValidationErrorElement" Color="{StaticResource Color_028}" />
								<SolidColorBrush x:Key="HScrollbarThumbBackgroundBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="VScrollbarThumbBackgroundBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ScrollbarPageButtonArrowBackgroundBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ScrollbarPageButtonArrowPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ScrollbarPageButtonArrowHoverBackgroundBrush" Color="{StaticResource Color_002}" />
								<SolidColorBrush x:Key="ScrollbarPageButtonArrowDisabledBackgroundBrush" Color="{StaticResource Color_005}" />
								<SolidColorBrush x:Key="VScrollbarThumbHoverBackgroundBrush" Color="{StaticResource Color_002}" />
								<SolidColorBrush x:Key="HScrollbarThumbHoverBackgroundBrush" Color="{StaticResource Color_002}" />
								<SolidColorBrush x:Key="VScrollbarThumbPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="HScrollbarThumbPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="VScrollbarThumbDisabledBackgroundBrush" Color="{StaticResource Color_005}" />
								<SolidColorBrush x:Key="HScrollbarThumbDisabledBackgroundBrush" Color="{StaticResource Color_005}" />
								<SolidColorBrush x:Key="ScrollbarDisabledBackgroundBrush" Color="{StaticResource Color_007}" />
								<SolidColorBrush x:Key="ScrollbarBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="ComboBoxBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="ComboBoxBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="ComboBoxReadOnlyBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="ComboBoxHoverBackgroundBrush" Color="{StaticResource Color_007}" />
								<SolidColorBrush x:Key="ComboBoxHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ComboBoxFocusedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ComboBoxDisabledBackgroundBrush" Color="{StaticResource Color_012}" />
								<SolidColorBrush x:Key="ComboBoxReadOnlyBackgroundBrush" Color="{StaticResource Color_064}" />
								<SolidColorBrush x:Key="PopupBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="PopupBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="TextBoxBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="TextBoxBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="TextBoxHoverBackgroundBrush" Color="{StaticResource Color_008}" />
								<SolidColorBrush x:Key="TextBoxHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="TextBoxFocusedBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="TextBoxReadOnlyBackgroundBrush" Color="{StaticResource Color_064}" />
								<SolidColorBrush x:Key="TextBoxSelectionBackgroundBrush" Color="{StaticResource Color_024}" Opacity="0.4" />
								<SolidColorBrush x:Key="TextBoxSelectionForegroundBrush" Color="{StaticResource Color_035}" />
								<SolidColorBrush x:Key="ButtonBackgroundBrush" Color="{StaticResource Color_008}" />
								<SolidColorBrush x:Key="ButtonBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="ButtonHoverBackgroundBrush" Color="{StaticResource Color_006}" />
								<SolidColorBrush x:Key="ButtonHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ButtonPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ButtonPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ComboBoxItemHoverBackgroundBrush" Color="{StaticResource Color_006}" />
								<SolidColorBrush x:Key="ComboBoxItemHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ComboBoxItemPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ComboBoxItemPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ComboBoxToggleButtonBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="ComboBoxToggleButtonPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ComboBoxToggleButtonDropDownSeparatorBackgroundBrush" Color="{StaticResource Color_006}" />
								<SolidColorBrush x:Key="ComboBoxToggleButtonPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ListBoxBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="ListBoxBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="ListBoxItemBackgroundBrush" Color="{StaticResource Color_016}" />
								<SolidColorBrush x:Key="ListBoxItemBorderBrush" Color="{StaticResource Color_016}" />
								<SolidColorBrush x:Key="ListBoxItemHoverBackgroundBrush" Color="{StaticResource Color_006}" />
								<SolidColorBrush x:Key="ListBoxItemHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="ListBoxItemPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ListBoxItemPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="ListBoxItemSelectedBackgroundBrush" Color="{StaticResource Color_026}" />
								<SolidColorBrush x:Key="ListBoxItemSelectedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="CheckBoxBackgroundlBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxHoverBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxPressedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxFocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxInvalidUnfocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxInvalidFocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="CheckBoxBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="CheckBoxHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="CheckBoxPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="CheckBoxFocusedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="CheckBoxInvalidUnfocusedBorderBrush" Color="{StaticResource Color_029}" />
								<SolidColorBrush x:Key="CheckBoxInvalidFocusedBorderBrush" Color="{StaticResource Color_028}" />
								<SolidColorBrush x:Key="CheckBoxIndeterminateCheckBackgroundBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="CheckBoxCheckBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="RadioButtonBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonHoverBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonPressedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonFocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonInvalidUnfocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonInvalidFocusedBackgroundBrush" Color="{StaticResource Color_009}" />
								<SolidColorBrush x:Key="RadioButtonBorderBrush" Color="{StaticResource Color_004}" />
								<SolidColorBrush x:Key="RadioButtonHoverBorderBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="RadioButtonPressedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="RadioButtonFocusedBorderBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="RadioButtonInvalidUnfocusedBorderBrush" Color="{StaticResource Color_029}" />
								<SolidColorBrush x:Key="RadioButtonInvalidFocusedBorderBrush" Color="{StaticResource Color_028}" />
								<SolidColorBrush x:Key="RadioButtonCheckBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="GlyphBackgroundBrush" Color="{StaticResource Color_003}" />
								<SolidColorBrush x:Key="GlyphHoverBackgroundBrush" Color="{StaticResource Color_002}" />
								<SolidColorBrush x:Key="GlyphPressedBackgroundBrush" Color="{StaticResource Color_024}" />
								<SolidColorBrush x:Key="GlyphDisabledBackgroundBrush" Color="{StaticResource Color_005}" />
								<SolidColorBrush x:Key="ValidationToolTipTemplateShadowBrush" Color="{StaticResource Color_003}" />
								<ControlTemplate x:Key="ValidationToolTipTemplate">
									<Grid x:Name="Root" Margin="5,0" Opacity="0" RenderTransformOrigin="0,0">
										<Grid.RenderTransform>
											<TranslateTransform x:Name="xform" X="-25" />
										</Grid.RenderTransform>
										<VisualStateManager.VisualStateGroups>
											<VisualStateGroup x:Name="OpenStates">
												<VisualStateGroup.Transitions>
													<VisualTransition GeneratedDuration="0" />
													<VisualTransition GeneratedDuration="0:0:0.2" To="Open">
														<Storyboard>
															<DoubleAnimation Duration="0:0:0.2" To="0" Storyboard.TargetProperty="X" Storyboard.TargetName="xform">
																<DoubleAnimation.EasingFunction>
																	<BackEase Amplitude=".3" EasingMode="EaseOut" />
																</DoubleAnimation.EasingFunction>
															</DoubleAnimation>
															<DoubleAnimation Duration="0:0:0.2" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
														</Storyboard>
													</VisualTransition>
												</VisualStateGroup.Transitions>
												<VisualState x:Name="Closed">
													<Storyboard>
														<DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
													</Storyboard>
												</VisualState>
												<VisualState x:Name="Open">
													<Storyboard>
														<DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="X" Storyboard.TargetName="xform" />
														<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
													</Storyboard>
												</VisualState>
											</VisualStateGroup>
										</VisualStateManager.VisualStateGroups>
										<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="4,4,-4,-4" Opacity="0.02" />
										<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="3,3,-3,-3" Opacity="0.08" />
										<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="2,2,-2,-2" Opacity="0.15" />
										<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="1,1,-1,-1" Opacity="0.21" />
										<Border Background="{StaticResource ValidationErrorElement}" />
										<Border >
											<TextBlock Foreground="{StaticResource LightForegroundBrush}" MaxWidth="250" Margin="8,4,8,4" TextWrapping="Wrap" Text="{Binding (Validation.Errors)[0].ErrorContent}" UseLayoutRounding="false" />
										</Border>
									</Grid>
								</ControlTemplate>
								<Style x:Key="ComboBoxToggleButtonStyle" TargetType="ToggleButton">
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="BorderBrush" Value="{StaticResource ComboBoxToggleButtonBorderBrush}" />
									<Setter Property="MinWidth" Value="30" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="BorderThickness" Value="1" />
									<Setter Property="Padding" Value="2" />
									<Setter Property="Cursor" Value="Hand" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="ToggleButton">
												<Grid>
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource GlyphHoverBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Pressed">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource GlyphPressedBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource GlyphDisabledBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="CheckStates">
															<VisualState x:Name="Checked">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="ArrowSelected">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unchecked" />
															<VisualState x:Name="Indeterminate" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused" />
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Grid.ColumnDefinitions>
														<ColumnDefinition />
														<ColumnDefinition Width="30" />
													</Grid.ColumnDefinitions>
													<Rectangle x:Name="Bd" Fill="{StaticResource TransparentBrush}" Grid.ColumnSpan="2" />
													<Grid Grid.Column="1">
														<Rectangle Width="1" Fill="{StaticResource ComboBoxToggleButtonDropDownSeparatorBackgroundBrush}" HorizontalAlignment="Left" Margin="-1,5,0,5" />
														<Path x:Name="Arrow" Width="10" Height="6" Fill="{StaticResource GlyphBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" />
														<Path x:Name="ArrowSelected" Width="10" Height="6" Visibility="Collapsed" Fill="{StaticResource GlyphPressedBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" />
													</Grid>
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
								<Style x:Key="ComboBoxItemStyle" TargetType="ComboBoxItem">
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="Padding" Value="6,0" />
									<Setter Property="HorizontalContentAlignment" Value="Left" />
									<Setter Property="VerticalContentAlignment" Value="Center" />
									<Setter Property="Background" Value="{StaticResource TransparentBrush}" />
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="BorderThickness" Value="1" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="ComboBoxItem">
												<Grid Background="{TemplateBinding Background}">
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="fillColor" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="DisabledVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="SelectionStates">
															<VisualState x:Name="Unselected" />
															<VisualState x:Name="Selected">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="CheckedBd">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="contentControl">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Collapsed</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="contentControl1">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="SelectedUnfocused" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Visibility" Storyboard.TargetName="FocusVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="LayoutStates">
															<VisualState x:Name="AfterLoaded" />
															<VisualState x:Name="BeforeLoaded" />
															<VisualState x:Name="BeforeUnloaded" />
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Rectangle Fill="{StaticResource TransparentBrush}" />
													<Rectangle x:Name="fillColor" Fill="{StaticResource ComboBoxItemHoverBackgroundBrush}" IsHitTestVisible="False" Opacity="0" Stroke="{StaticResource ComboBoxItemHoverBorderBrush}" StrokeThickness="{TemplateBinding BorderThickness}" />
													<Rectangle x:Name="CheckedBd" Fill="{StaticResource ComboBoxItemPressedBackgroundBrush}" IsHitTestVisible="False" Visibility="Collapsed" Stroke="{StaticResource ComboBoxItemPressedBorderBrush}" StrokeThickness="{TemplateBinding BorderThickness}" />
													<ContentControl x:Name="contentControl" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" Margin="{TemplateBinding Padding}" Foreground="{TemplateBinding Foreground}">
														<ContentPresenter x:Name="contentPresenter" />
													</ContentControl>
													<ContentControl x:Name="contentControl1" Visibility="Collapsed" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" Margin="{TemplateBinding Padding}" Foreground="{StaticResource LightForegroundBrush}">
														<ContentPresenter x:Name="contentPresenter1" />
													</ContentControl>
													<Rectangle x:Name="FocusVisualElement" Stroke="{StaticResource ComboBoxItemPressedBackgroundBrush}" Visibility="Collapsed" StrokeThickness="2" />
													<Rectangle x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Visibility="Collapsed" />
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
								<Style x:Key="ListBoxItemStyle" TargetType="ListBoxItem">
									<Setter Property="Background" Value="{StaticResource TransparentBrush}" />
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="Padding" Value="6,2" />
									<Setter Property="Margin" Value="0" />
									<Setter Property="HorizontalContentAlignment" Value="Stretch" />
									<Setter Property="VerticalContentAlignment" Value="Center" />
									<Setter Property="BorderThickness" Value="1" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="ListBoxItem">
												<Grid>
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ListBoxItemHoverBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ListBoxItemHoverBorderBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="DisabledVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="SelectionStates">
															<VisualState x:Name="Unselected" />
															<VisualState x:Name="Selected">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="BgSelected">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="SelectedUnfocused">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="BgSelected">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="FocusedVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Rectangle x:Name="Bd" Fill="{TemplateBinding Background}" />
													<Rectangle x:Name="BgSelected" Fill="{StaticResource ListBoxItemSelectedBackgroundBrush}" Stroke="{StaticResource ListBoxItemSelectedBorderBrush}" Visibility="Collapsed" />
													<ContentControl x:Name="ContentControl" Foreground="{TemplateBinding Foreground}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" HorizontalContentAlignment="{TemplateBinding HorizontalContentAlignment}">
														<ContentPresenter x:Name="contentPresenter" />
													</ContentControl>
													<Rectangle x:Name="FocusedVisualElement" IsHitTestVisible="False" Visibility="Collapsed" Stroke="{StaticResource ListBoxItemPressedBorderBrush}" StrokeThickness="2" />
													<Rectangle x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Visibility="Collapsed" />
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
								<Style x:Key="CheckBoxStyle" TargetType="CheckBox">
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="HorizontalContentAlignment" Value="Left" />
									<Setter Property="VerticalContentAlignment" Value="Center" />
									<Setter Property="Padding" Value="6,0,0,0" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="MinWidth" Value="30" />
									<Setter Property="BorderThickness" Value="1" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="CheckBox">
												<Grid VerticalAlignment="{TemplateBinding VerticalContentAlignment}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}">
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="hover" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Pressed">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="pressed" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<DoubleAnimation Duration="0" To=".55" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="contentPresenter" />
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="disabled" />
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="CheckStates">
															<VisualState x:Name="Checked">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="checkBox" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unchecked" />
															<VisualState x:Name="Indeterminate">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="IndeterminateCheck" />
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="focused" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="ValidationStates">
															<VisualState x:Name="Valid" />
															<VisualState x:Name="InvalidUnfocused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="invalidUnfocused" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="InvalidFocused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="invalidFocused" />
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Grid.ColumnDefinitions>
														<ColumnDefinition Width="30" />
														<ColumnDefinition Width="*" />
													</Grid.ColumnDefinitions>
													<Rectangle Fill="{StaticResource TransparentBrush}" />
													<Rectangle x:Name="normal" Opacity="1" Stroke="{StaticResource CheckBoxBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxBackgroundlBrush}" Width="18" Height="18" />
													<Rectangle x:Name="hover" Stroke="{StaticResource CheckBoxHoverBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxHoverBackgroundBrush}" Opacity="0" Width="18" Height="18" />
													<Rectangle x:Name="pressed" Opacity="0" Stroke="{StaticResource CheckBoxPressedBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxPressedBackgroundBrush}" Width="18" Height="18" />
													<Rectangle x:Name="focused" Opacity="0" Stroke="{StaticResource CheckBoxFocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxFocusedBackgroundBrush}" Width="18" Height="18" />
													<Rectangle x:Name="invalidUnfocused" Opacity="0" Stroke="{StaticResource CheckBoxInvalidUnfocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxInvalidUnfocusedBackgroundBrush}" Width="18" Height="18" />
													<Rectangle x:Name="invalidFocused" Opacity="0" Stroke="{StaticResource CheckBoxInvalidFocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource CheckBoxInvalidFocusedBackgroundBrush}" Width="18" Height="18" />
													<Path x:Name="checkBox" Height="10" Width="12" Stretch="Fill" Opacity="0" Data="M 1145.607177734375,430 C1145.607177734375,430 1141.449951171875,435.0772705078125 1141.449951171875,435.0772705078125 1141.449951171875,435.0772705078125 1139.232177734375,433.0999755859375 1139.232177734375,433.0999755859375 1139.232177734375,433.0999755859375 1138,434.5538330078125 1138,434.5538330078125 1138,434.5538330078125 1141.482177734375,438 1141.482177734375,438 1141.482177734375,438 1141.96875,437.9375 1141.96875,437.9375 1141.96875,437.9375 1147,431.34619140625 1147,431.34619140625 1147,431.34619140625 1145.607177734375,430 1145.607177734375,430 z" Fill="{StaticResource CheckBoxCheckBackgroundBrush}" UseLayoutRounding="False" />
													<Rectangle x:Name="IndeterminateCheck" Fill="{StaticResource CheckBoxIndeterminateCheckBackgroundBrush}" Height="3" Width="8" Opacity="0" />
													<Rectangle x:Name="disabled" Opacity="0" StrokeThickness="1" Fill="{StaticResource DisabledVisualElement}" Width="18" Height="18" />
													<ContentPresenter x:Name="contentPresenter" ContentTemplate="{TemplateBinding ContentTemplate}" Content="{TemplateBinding Content}" Grid.Column="1" Margin="{TemplateBinding Padding}" />
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
								<Style x:Key="RadioButtonStyle" TargetType="RadioButton">
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="HorizontalContentAlignment" Value="Left" />
									<Setter Property="VerticalContentAlignment" Value="Center" />
									<Setter Property="Padding" Value="6,0,0,0" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="MinWidth" Value="20" />
									<Setter Property="BorderThickness" Value="1" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="RadioButton">
												<Grid>
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="hover" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Pressed">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="pressed" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<DoubleAnimation Duration="0" To=".55" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="contentPresenter" />
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="disabled" />
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="CheckStates">
															<VisualState x:Name="Checked">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="Checked1" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unchecked" />
															<VisualState x:Name="Indeterminate" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="focused" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
														<VisualStateGroup x:Name="ValidationStates">
															<VisualState x:Name="Valid" />
															<VisualState x:Name="InvalidUnfocused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="invalidUnfocused" />
																</Storyboard>
															</VisualState>
															<VisualState x:Name="InvalidFocused">
																<Storyboard>
																	<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="invalidFocused" />
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Grid.ColumnDefinitions>
														<ColumnDefinition Width="18" />
														<ColumnDefinition Width="*" />
													</Grid.ColumnDefinitions>
													<Rectangle Fill="{StaticResource TransparentBrush}" Margin="-6,0" />
													<Ellipse x:Name="normal" Opacity="1" Stroke="{StaticResource RadioButtonBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonBackgroundBrush}" Width="18" Height="18" />
													<Ellipse x:Name="hover" Stroke="{StaticResource RadioButtonHoverBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonHoverBackgroundBrush}" Opacity="0" Width="18" Height="18" />
													<Ellipse x:Name="pressed" Opacity="0" Stroke="{StaticResource RadioButtonPressedBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonPressedBackgroundBrush}" Width="18" Height="18" />
													<Ellipse x:Name="focused" Opacity="0" Stroke="{StaticResource RadioButtonFocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonFocusedBackgroundBrush}" Width="18" Height="18" />
													<Ellipse x:Name="invalidUnfocused" Opacity="0" Stroke="{StaticResource RadioButtonInvalidUnfocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonInvalidUnfocusedBackgroundBrush}" Width="18" Height="18" />
													<Ellipse x:Name="invalidFocused" Opacity="0" Stroke="{StaticResource RadioButtonInvalidFocusedBorderBrush}" StrokeThickness="1" Fill="{StaticResource RadioButtonInvalidFocusedBackgroundBrush}" Width="18" Height="18" />
													<Ellipse x:Name="Checked1" Fill="{StaticResource RadioButtonCheckBackgroundBrush}" Opacity="0" Width="10" Height="10" />
													<ContentPresenter x:Name="contentPresenter" ContentTemplate="{TemplateBinding ContentTemplate}" Content="{TemplateBinding Content}" Grid.Column="1" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" />
													<Ellipse x:Name="disabled" Opacity="0" StrokeThickness="1" Fill="{StaticResource DisabledVisualElement}" Width="18" Height="18" />
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
								<Style x:Key="ButtonStyle" TargetType="Button">
									<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
									<Setter Property="FontSize" Value="14.667" />
									<Setter Property="FontFamily" Value="Segoe UI" />
									<Setter Property="Padding" Value="10,0,10,2" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="MinWidth" Value="30" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="Button">
												<Grid>
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBorderBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Pressed">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBackgroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBorderBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																	<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Foreground" Storyboard.TargetName="ContentControl">
																		<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource LightForegroundBrush}" />
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="DisabledVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
														</VisualStateGroup>
														<VisualStateGroup x:Name="FocusStates">
															<VisualState x:Name="Focused">
																<Storyboard>
																	<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="FocusedVisualElement">
																		<DiscreteObjectKeyFrame KeyTime="0">
																			<DiscreteObjectKeyFrame.Value>
																				<Visibility>Visible</Visibility>
																			</DiscreteObjectKeyFrame.Value>
																		</DiscreteObjectKeyFrame>
																	</ObjectAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Unfocused" />
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Rectangle x:Name="Bd" Fill="{StaticResource ButtonBackgroundBrush}" Stroke="{StaticResource ButtonBorderBrush}" StrokeThickness="1" />
													<ContentControl x:Name="ContentControl" Foreground="{TemplateBinding Foreground}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
														<ContentPresenter x:Name="contentPresenter" />
													</ContentControl>
													<Rectangle x:Name="FocusedVisualElement" Stroke="{StaticResource ButtonPressedBorderBrush}" Visibility="Collapsed" StrokeThickness="2" />
													<Rectangle x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Visibility="Collapsed" />
												</Grid>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Style>
							</ResourceDictionary>
						</ResourceDictionary.MergedDictionaries>
						<Style x:Key="ScrollBarButtonStyle" TargetType="{x:Type RepeatButton}">
							<Setter Property="MinWidth" Value="30" />
							<Setter Property="MinHeight" Value="30" />
							<Setter Property="Padding" Value="0" />
							<Setter Property="OverridesDefaultStyle" Value="true" />
							<Setter Property="Focusable" Value="false" />
							<Setter Property="IsTabStop" Value="false" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type RepeatButton}">
										<Grid x:Name="grid1">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ScrollbarPageButtonArrowHoverBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Pressed">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ScrollbarPageButtonArrowPressedBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Disabled">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Arrow">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ScrollbarPageButtonArrowDisabledBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Rectangle Fill="{StaticResource TransparentBrush}" Margin="-5" />
											<Path x:Name="Arrow" Data="F1 M 541.537,173.589L 531.107,173.589L 536.322,167.49L 541.537,173.589 Z " Height="6" Stretch="Uniform" Width="10" Fill="{StaticResource ScrollbarPageButtonArrowBackgroundBrush}" Margin="{TemplateBinding Padding}" />
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<Style x:Key="ScrollBarPageButtonStyle" TargetType="{x:Type RepeatButton}">
							<Setter Property="OverridesDefaultStyle" Value="true" />
							<Setter Property="Background" Value="Transparent" />
							<Setter Property="Focusable" Value="false" />
							<Setter Property="IsTabStop" Value="false" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type RepeatButton}">
										<Rectangle Fill="{TemplateBinding Background}" Height="{TemplateBinding Height}" Width="{TemplateBinding Width}">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver" />
													<VisualState x:Name="Pressed" />
													<VisualState x:Name="Disabled" />
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
										</Rectangle>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<Style x:Key="HScrollBarThumbStyle" TargetType="{x:Type Thumb}">
							<Setter Property="MinWidth" Value="20" />
							<Setter Property="MinHeight" Value="30" />
							<Setter Property="OverridesDefaultStyle" Value="true" />
							<Setter Property="IsTabStop" Value="false" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type Thumb}">
										<Grid Margin="0">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource HScrollbarThumbHoverBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Pressed">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource HScrollbarThumbPressedBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Disabled">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource HScrollbarThumbDisabledBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Rectangle Fill="{StaticResource TransparentBrush}" Margin="-5" />
											<Rectangle x:Name="Thumb" Margin="1" Fill="{StaticResource HScrollbarThumbBackgroundBrush}" Height="8" />
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<Style x:Key="VScrollBarThumbStyle" TargetType="{x:Type Thumb}">
							<Setter Property="OverridesDefaultStyle" Value="true" />
							<Setter Property="MinWidth" Value="30" />
							<Setter Property="MinHeight" Value="20" />
							<Setter Property="Stylus.IsPressAndHoldEnabled" Value="false" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type Thumb}">
										<Grid x:Name="grid" Height="Auto" Width="Auto">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource VScrollbarThumbHoverBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Pressed">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource VScrollbarThumbPressedBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Disabled">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Fill" Storyboard.TargetName="Thumb">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource VScrollbarThumbDisabledBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Rectangle Fill="{StaticResource TransparentBrush}" Margin="-5" />
											<Rectangle x:Name="Thumb" Fill="{StaticResource VScrollbarThumbBackgroundBrush}" Width="8" />
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<Style x:Key="ScrollBarStyle" TargetType="{x:Type ScrollBar}">
							<Setter Property="Stylus.IsPressAndHoldEnabled" Value="false" />
							<Setter Property="Stylus.IsFlicksEnabled" Value="false" />
							<Setter Property="Width" Value="30" />
							<Setter Property="MinWidth" Value="30" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type ScrollBar}">
										<Grid x:Name="Bg" SnapsToDevicePixels="true">
											<Grid.RowDefinitions>
												<RowDefinition Height="30" />
												<RowDefinition Height="0.00001*" />
												<RowDefinition Height="30" />
											</Grid.RowDefinitions>
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualStateGroup.Transitions>
														<VisualTransition GeneratedDuration="0:0:0.3" />
													</VisualStateGroup.Transitions>
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver" />
													<VisualState x:Name="Disabled">
														<Storyboard>
															<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="repeatButton">
																<EasingDoubleKeyFrame KeyTime="0" Value="0.6" />
															</DoubleAnimationUsingKeyFrames>
															<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="repeatButton1">
																<EasingDoubleKeyFrame KeyTime="0" Value="0.6" />
															</DoubleAnimationUsingKeyFrames>
															<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="thumb">
																<EasingDoubleKeyFrame KeyTime="0" Value="0" />
															</DoubleAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Rectangle Grid.RowSpan="3" StrokeThickness="1" Fill="{StaticResource TransparentBrush}" Stroke="{StaticResource TransparentBrush}" Margin="0" />
											<RepeatButton x:Name="repeatButton" Command="{x:Static ScrollBar.LineUpCommand}" IsEnabled="True" Style="{StaticResource ScrollBarButtonStyle}" HorizontalAlignment="Center" />
											<Track x:Name="PART_Track" IsDirectionReversed="true" IsEnabled="True" Grid.Row="1">
												<Track.DecreaseRepeatButton>
													<RepeatButton Command="{x:Static ScrollBar.PageUpCommand}" Style="{StaticResource ScrollBarPageButtonStyle}" />
												</Track.DecreaseRepeatButton>
												<Track.IncreaseRepeatButton>
													<RepeatButton Command="{x:Static ScrollBar.PageDownCommand}" Style="{StaticResource ScrollBarPageButtonStyle}" />
												</Track.IncreaseRepeatButton>
												<Track.Thumb>
													<Thumb x:Name="thumb" Style="{StaticResource VScrollBarThumbStyle}" HorizontalAlignment="Center" Width="30" />
												</Track.Thumb>
											</Track>
											<RepeatButton x:Name="repeatButton1" Command="{x:Static ScrollBar.LineDownCommand}" IsEnabled="True" Grid.Row="2" Style="{StaticResource ScrollBarButtonStyle}" RenderTransformOrigin="0.5,0.5" HorizontalAlignment="Center">
												<RepeatButton.RenderTransform>
													<TransformGroup>
														<ScaleTransform />
														<SkewTransform />
														<RotateTransform Angle="180" />
														<TranslateTransform />
													</TransformGroup>
												</RepeatButton.RenderTransform>
											</RepeatButton>
										</Grid>
										<ControlTemplate.Triggers>
											<Trigger Property="IsEnabled" Value="false">
												<Setter Property="Background" TargetName="Bg" Value="{StaticResource ScrollbarDisabledBackgroundBrush}" />
											</Trigger>
										</ControlTemplate.Triggers>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
							<Style.Triggers>
								<Trigger Property="Orientation" Value="Horizontal">
									<Setter Property="Width" Value="Auto" />
									<Setter Property="MinWidth" Value="0" />
									<Setter Property="Height" Value="30" />
									<Setter Property="MinHeight" Value="30" />
									<Setter Property="Template">
										<Setter.Value>
											<ControlTemplate TargetType="{x:Type ScrollBar}">
												<Grid x:Name="Bg" SnapsToDevicePixels="true">
													<Grid.ColumnDefinitions>
														<ColumnDefinition Width="30" />
														<ColumnDefinition Width="0.00001*" />
														<ColumnDefinition Width="30" />
													</Grid.ColumnDefinitions>
													<VisualStateManager.VisualStateGroups>
														<VisualStateGroup x:Name="CommonStates">
															<VisualStateGroup.Transitions>
																<VisualTransition GeneratedDuration="0:0:0.3" />
															</VisualStateGroup.Transitions>
															<VisualState x:Name="Normal" />
															<VisualState x:Name="MouseOver">
																<Storyboard>
																	<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="repeatButton">
																		<EasingDoubleKeyFrame KeyTime="0" Value="1" />
																	</DoubleAnimationUsingKeyFrames>
																	<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="repeatButton1">
																		<EasingDoubleKeyFrame KeyTime="0" Value="1" />
																	</DoubleAnimationUsingKeyFrames>
																</Storyboard>
															</VisualState>
															<VisualState x:Name="Disabled" />
														</VisualStateGroup>
													</VisualStateManager.VisualStateGroups>
													<Rectangle Grid.ColumnSpan="5" StrokeThickness="1" Fill="{StaticResource TransparentBrush}" Stroke="{StaticResource TransparentBrush}" />
													<RepeatButton x:Name="repeatButton" Command="{x:Static ScrollBar.LineLeftCommand}" IsEnabled="True" Style="{DynamicResource ScrollBarButtonStyle}" Opacity="1" RenderTransformOrigin="0.5,0.5" VerticalAlignment="Center">
														<RepeatButton.RenderTransform>
															<TransformGroup>
																<ScaleTransform />
																<SkewTransform />
																<RotateTransform Angle="-90" />
																<TranslateTransform />
															</TransformGroup>
														</RepeatButton.RenderTransform>
													</RepeatButton>
													<Track x:Name="PART_Track" Grid.Column="1" IsEnabled="True">
														<Track.DecreaseRepeatButton>
															<RepeatButton Command="{x:Static ScrollBar.PageLeftCommand}" Style="{StaticResource ScrollBarPageButtonStyle}" />
														</Track.DecreaseRepeatButton>
														<Track.IncreaseRepeatButton>
															<RepeatButton Command="{x:Static ScrollBar.PageRightCommand}" Style="{StaticResource ScrollBarPageButtonStyle}" />
														</Track.IncreaseRepeatButton>
														<Track.Thumb>
															<Thumb Style="{StaticResource HScrollBarThumbStyle}" VerticalAlignment="Center" Height="30" />
														</Track.Thumb>
													</Track>
													<RepeatButton x:Name="repeatButton1" Grid.Column="2" Command="{x:Static ScrollBar.LineRightCommand}" IsEnabled="True" Style="{DynamicResource ScrollBarButtonStyle}" Opacity="1" RenderTransformOrigin="0.5,0.5" VerticalAlignment="Center">
														<RepeatButton.RenderTransform>
															<TransformGroup>
																<ScaleTransform />
																<SkewTransform />
																<RotateTransform Angle="90" />
																<TranslateTransform />
															</TransformGroup>
														</RepeatButton.RenderTransform>
													</RepeatButton>
												</Grid>
												<ControlTemplate.Triggers>
													<Trigger Property="IsEnabled" Value="false">
														<Setter Property="Background" TargetName="Bg" Value="{StaticResource ScrollbarDisabledBackgroundBrush}" />
													</Trigger>
												</ControlTemplate.Triggers>
											</ControlTemplate>
										</Setter.Value>
									</Setter>
								</Trigger>
							</Style.Triggers>
						</Style>
						<Style x:Key="ScrollViewerStyle" TargetType="{x:Type ScrollViewer}">
							<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
							<Setter Property="HorizontalContentAlignment" Value="Left" />
							<Setter Property="VerticalContentAlignment" Value="Top" />
							<Setter Property="VerticalScrollBarVisibility" Value="Auto" />
							<Setter Property="Padding" Value="0" />
							<Setter Property="BorderThickness" Value="1" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type ScrollViewer}">
										<Grid x:Name="Grid">
											<Grid.ColumnDefinitions>
												<ColumnDefinition Width="*" />
												<ColumnDefinition Width="Auto" />
											</Grid.ColumnDefinitions>
											<Grid.RowDefinitions>
												<RowDefinition Height="*" />
												<RowDefinition Height="Auto" />
											</Grid.RowDefinitions>
											<ScrollContentPresenter x:Name="PART_ScrollContentPresenter" CanContentScroll="{TemplateBinding CanContentScroll}" CanHorizontallyScroll="False" CanVerticallyScroll="False" ContentTemplate="{TemplateBinding ContentTemplate}" Content="{TemplateBinding Content}" Grid.Column="0" Margin="{TemplateBinding Padding}" Grid.Row="0" />
											<ScrollBar x:Name="PART_VerticalScrollBar" AutomationProperties.AutomationId="VerticalScrollBar" Cursor="Arrow" Grid.Column="1" Maximum="{TemplateBinding ScrollableHeight}" Minimum="0" Grid.Row="0" Visibility="{TemplateBinding ComputedVerticalScrollBarVisibility}" Value="{Binding VerticalOffset, Mode=OneWay, RelativeSource={RelativeSource TemplatedParent}}" ViewportSize="{TemplateBinding ViewportHeight}" Style="{StaticResource ScrollBarStyle}" />
											<ScrollBar x:Name="PART_HorizontalScrollBar" AutomationProperties.AutomationId="HorizontalScrollBar" Cursor="Arrow" Grid.Column="0" Maximum="{TemplateBinding ScrollableWidth}" Minimum="0" Orientation="Horizontal" Grid.Row="1" Visibility="{TemplateBinding ComputedHorizontalScrollBarVisibility}" Value="{Binding HorizontalOffset, Mode=OneWay, RelativeSource={RelativeSource TemplatedParent}}" ViewportSize="{TemplateBinding ViewportWidth}" Style="{StaticResource ScrollBarStyle}" />
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<ControlTemplate x:Key="TextBoxValidationToolTipTemplate">
							<Grid x:Name="Root" Margin="5,0" Opacity="0" RenderTransformOrigin="0,0">
								<Grid.RenderTransform>
									<TranslateTransform x:Name="xform" X="-25" />
								</Grid.RenderTransform>
								<VisualStateManager.VisualStateGroups>
									<VisualStateGroup x:Name="OpenStates">
										<VisualStateGroup.Transitions>
											<VisualTransition GeneratedDuration="0" />
											<VisualTransition GeneratedDuration="0:0:0.2" To="Open">
												<Storyboard>
													<DoubleAnimation Duration="0:0:0.2" To="0" Storyboard.TargetProperty="X" Storyboard.TargetName="xform">
														<DoubleAnimation.EasingFunction>
															<BackEase Amplitude=".3" EasingMode="EaseOut" />
														</DoubleAnimation.EasingFunction>
													</DoubleAnimation>
													<DoubleAnimation Duration="0:0:0.2" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
												</Storyboard>
											</VisualTransition>
										</VisualStateGroup.Transitions>
										<VisualState x:Name="Closed">
											<Storyboard>
												<DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
											</Storyboard>
										</VisualState>
										<VisualState x:Name="Open">
											<Storyboard>
												<DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="X" Storyboard.TargetName="xform" />
												<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="Root" />
											</Storyboard>
										</VisualState>
									</VisualStateGroup>
								</VisualStateManager.VisualStateGroups>
								<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="4,4,-4,-4" Opacity="0.02" />
								<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="3,3,-3,-3" Opacity="0.08" />
								<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="2,2,-2,-2" Opacity="0.15" />
								<Border Background="{StaticResource ValidationToolTipTemplateShadowBrush}" Margin="1,1,-1,-1" Opacity="0.21" />
								<Border Background="{StaticResource ValidationErrorElement}" />
								<Border >
									<TextBlock Foreground="{StaticResource LightForegroundBrush}" MaxWidth="250" Margin="8,4,8,4" TextWrapping="Wrap" Text="{Binding (Validation.Errors).CurrentItem.ErrorContent}" UseLayoutRounding="false" />
								</Border>
							</Grid>
						</ControlTemplate>
						<Style x:Key="ComboBoxEditableTextBoxStyle" TargetType="{x:Type TextBox}">
							<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
							<Setter Property="FontSize" Value="14.667" />
							<Setter Property="FontFamily" Value="Segoe UI" />
							<Setter Property="OverridesDefaultStyle" Value="true" />
							<Setter Property="AllowDrop" Value="true" />
							<Setter Property="MinWidth" Value="0" />
							<Setter Property="MinHeight" Value="30" />
							<Setter Property="Padding" Value="6,4" />
							<Setter Property="FocusVisualStyle" Value="{x:Null}" />
							<Setter Property="SelectionBrush" Value="{StaticResource TextBoxFocusedBrush}" />
							<Setter Property="SelectionOpacity" Value="0.4" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type TextBox}">
										<ScrollViewer Style="{StaticResource ScrollViewerStyle}" x:Name="PART_ContentHost" Background="Transparent" Focusable="false" HorizontalScrollBarVisibility="Hidden" VerticalScrollBarVisibility="Hidden">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="Disabled">
														<Storyboard>
															<DoubleAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Opacity)" Storyboard.TargetName="PART_ContentHost">
																<EasingDoubleKeyFrame KeyTime="0" Value="0.3" />
															</DoubleAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="ReadOnly" />
													<VisualState x:Name="MouseOver" />
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
										</ScrollViewer>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<ControlTemplate x:Key="ComboBoxEditableTemplate" TargetType="{x:Type ComboBox}">
							<Grid x:Name="MainGrid" SnapsToDevicePixels="true">
								<Grid.ColumnDefinitions>
									<ColumnDefinition Width="*" />
									<ColumnDefinition Width="Auto" />
								</Grid.ColumnDefinitions>
								<VisualStateManager.VisualStateGroups>
									<VisualStateGroup x:Name="CommonStates">
										<VisualState x:Name="Normal" />
										<VisualState x:Name="MouseOver">
											<Storyboard>
												<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="hover">
													<DiscreteObjectKeyFrame KeyTime="0">
														<DiscreteObjectKeyFrame.Value>
															<Visibility>Visible</Visibility>
														</DiscreteObjectKeyFrame.Value>
													</DiscreteObjectKeyFrame>
												</ObjectAnimationUsingKeyFrames>
											</Storyboard>
										</VisualState>
										<VisualState x:Name="Disabled">
											<Storyboard>
												<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="disabled">
													<DiscreteObjectKeyFrame KeyTime="0">
														<DiscreteObjectKeyFrame.Value>
															<Visibility>Visible</Visibility>
														</DiscreteObjectKeyFrame.Value>
													</DiscreteObjectKeyFrame>
												</ObjectAnimationUsingKeyFrames>
											</Storyboard>
										</VisualState>
									</VisualStateGroup>
									<VisualStateGroup x:Name="FocusStates">
										<VisualState x:Name="Unfocused" />
										<VisualState x:Name="Focused">
											<Storyboard>
												<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="focused">
													<DiscreteObjectKeyFrame KeyTime="0">
														<DiscreteObjectKeyFrame.Value>
															<Visibility>Visible</Visibility>
														</DiscreteObjectKeyFrame.Value>
													</DiscreteObjectKeyFrame>
												</ObjectAnimationUsingKeyFrames>
											</Storyboard>
										</VisualState>
										<VisualState x:Name="FocusedDropDown">
											<Storyboard>
												<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="focused">
													<DiscreteObjectKeyFrame KeyTime="0">
														<DiscreteObjectKeyFrame.Value>
															<Visibility>Visible</Visibility>
														</DiscreteObjectKeyFrame.Value>
													</DiscreteObjectKeyFrame>
												</ObjectAnimationUsingKeyFrames>
											</Storyboard>
										</VisualState>
									</VisualStateGroup>
								</VisualStateManager.VisualStateGroups>
								<Rectangle x:Name="normal" Fill="{StaticResource ComboBoxBackgroundBrush}" Stroke="{StaticResource ComboBoxBorderBrush}" StrokeThickness="1" Grid.ColumnSpan="2" />
								<Rectangle x:Name="hover" Fill="{StaticResource ComboBoxHoverBackgroundBrush}" Stroke="{StaticResource ComboBoxHoverBorderBrush}" StrokeThickness="1" Visibility="Collapsed" Grid.ColumnSpan="2" />
								<Popup x:Name="PART_Popup" AllowsTransparency="true" Grid.ColumnSpan="2" IsOpen="{Binding IsDropDownOpen, RelativeSource={RelativeSource TemplatedParent}}" Margin="1" PopupAnimation="{DynamicResource {x:Static SystemParameters.ComboBoxPopupAnimationKey}}" Placement="Bottom">
									<Border x:Name="DropDownBorder" HorizontalAlignment="Stretch" Background="{StaticResource PopupBackgroundBrush}" BorderBrush="{StaticResource PopupBorderBrush}" BorderThickness="1" MaxHeight="{TemplateBinding MaxDropDownHeight}" MinWidth="{Binding ActualWidth, ElementName=MainGrid}" CornerRadius="2">
										<ScrollViewer x:Name="DropDownScrollViewer" Style="{StaticResource ScrollViewerStyle}">
											<Grid RenderOptions.ClearTypeHint="Enabled">
												<Canvas HorizontalAlignment="Left" Height="0" VerticalAlignment="Top" Width="0">
													<Rectangle x:Name="OpaqueRect" Fill="{Binding Background, ElementName=DropDownBorder}" Height="{Binding ActualHeight, ElementName=DropDownBorder}" Width="{Binding ActualWidth, ElementName=DropDownBorder}" />
												</Canvas>
												<ItemsPresenter x:Name="ItemsPresenter" KeyboardNavigation.DirectionalNavigation="Contained" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" />
											</Grid>
										</ScrollViewer>
									</Border>
								</Popup>
								<ToggleButton BorderBrush="{TemplateBinding BorderBrush}" Background="{TemplateBinding Background}" Grid.Column="0" IsChecked="{Binding IsDropDownOpen, Mode=TwoWay, RelativeSource={RelativeSource TemplatedParent}}" Style="{StaticResource ComboBoxToggleButtonStyle}" />
								<TextBox x:Name="PART_EditableTextBox" HorizontalContentAlignment="{TemplateBinding HorizontalContentAlignment}" IsReadOnly="{Binding IsReadOnly, RelativeSource={RelativeSource TemplatedParent}}" Style="{StaticResource ComboBoxEditableTextBoxStyle}" VerticalContentAlignment="{TemplateBinding VerticalContentAlignment}" Margin="0,0,31,0" />
								<Rectangle x:Name="focused" Stroke="{StaticResource ComboBoxFocusedBorderBrush}" StrokeThickness="1" Visibility="Collapsed" Grid.ColumnSpan="2" />
								<Rectangle x:Name="disabled" Fill="{StaticResource ComboBoxDisabledBackgroundBrush}" Visibility="Collapsed" Grid.ColumnSpan="2" />
							</Grid>
							<ControlTemplate.Triggers>
								<Trigger Property="HasItems" Value="false">
									<Setter Property="Height" TargetName="DropDownBorder" Value="95" />
								</Trigger>
							</ControlTemplate.Triggers>
						</ControlTemplate>
						<Style x:Key="ComboBoxStyle" TargetType="{x:Type ComboBox}">
							<Setter Property="Padding" Value="6,5,6,3" />
							<Setter Property="Margin" Value="0" />
							<Setter Property="FontSize" Value="14.667" />
							<Setter Property="FontFamily" Value="Segoe UI" />
							<Setter Property="MinHeight" Value="30" />
							<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
							<Setter Property="Background" Value="{StaticResource TransparentBrush}" />
							<Setter Property="BorderBrush" Value="{StaticResource ComboBoxBorderBrush}" />
							<Setter Property="ItemContainerStyle" Value="{StaticResource ComboBoxItemStyle}" />
							<Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Auto" />
							<Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Auto" />
							<Setter Property="ScrollViewer.CanContentScroll" Value="true" />
							<Setter Property="ScrollViewer.PanningMode" Value="Both" />
							<Setter Property="Stylus.IsFlicksEnabled" Value="False" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type ComboBox}">
										<Grid x:Name="MainGrid" SnapsToDevicePixels="true">
											<Grid.ColumnDefinitions>
												<ColumnDefinition Width="*" />
												<ColumnDefinition MinWidth="30" Width="0" />
											</Grid.ColumnDefinitions>
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="hover">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Disabled">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="disabled">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
												<VisualStateGroup x:Name="FocusStates">
													<VisualState x:Name="Unfocused" />
													<VisualState x:Name="Focused">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="focused">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="FocusedDropDown">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="focused">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Rectangle x:Name="normal" Fill="{StaticResource ComboBoxBackgroundBrush}" Stroke="{StaticResource ComboBoxBorderBrush}" StrokeThickness="1" Grid.ColumnSpan="2" />
											<Rectangle x:Name="hover" Fill="{StaticResource ComboBoxHoverBackgroundBrush}" Stroke="{StaticResource ComboBoxHoverBorderBrush}" StrokeThickness="1" Visibility="Collapsed" Grid.ColumnSpan="2" />
											<Popup x:Name="PART_Popup" AllowsTransparency="true" Grid.ColumnSpan="2" IsOpen="{Binding IsDropDownOpen, RelativeSource={RelativeSource TemplatedParent}}" Margin="1" PopupAnimation="{DynamicResource {x:Static SystemParameters.ComboBoxPopupAnimationKey}}" Placement="Bottom">
												<Border x:Name="DropDownBorder" HorizontalAlignment="Stretch" Background="{StaticResource PopupBackgroundBrush}" BorderBrush="{StaticResource PopupBorderBrush}" BorderThickness="1" MaxHeight="{TemplateBinding MaxDropDownHeight}" MinWidth="{Binding ActualWidth, ElementName=MainGrid}" CornerRadius="2">
													<ScrollViewer x:Name="DropDownScrollViewer" Style="{StaticResource ScrollViewerStyle}">
														<Grid RenderOptions.ClearTypeHint="Enabled">
															<Canvas HorizontalAlignment="Left" Height="0" VerticalAlignment="Top" Width="0">
																<Rectangle x:Name="OpaqueRect" Fill="{Binding Background, ElementName=DropDownBorder}" Height="{Binding ActualHeight, ElementName=DropDownBorder}" Width="{Binding ActualWidth, ElementName=DropDownBorder}" />
															</Canvas>
															<ItemsPresenter x:Name="ItemsPresenter" KeyboardNavigation.DirectionalNavigation="Contained" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" />
														</Grid>
													</ScrollViewer>
												</Border>
											</Popup>
											<ToggleButton BorderBrush="{TemplateBinding BorderBrush}" Background="{TemplateBinding Background}" Grid.ColumnSpan="2" IsChecked="{Binding IsDropDownOpen, Mode=TwoWay, RelativeSource={RelativeSource TemplatedParent}}" Style="{StaticResource ComboBoxToggleButtonStyle}" />
											<ContentPresenter ContentTemplate="{TemplateBinding SelectionBoxItemTemplate}" ContentTemplateSelector="{TemplateBinding ItemTemplateSelector}" Content="{TemplateBinding SelectionBoxItem}" ContentStringFormat="{TemplateBinding SelectionBoxItemStringFormat}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" IsHitTestVisible="false" Margin="{TemplateBinding Padding}" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" />
											<Rectangle x:Name="focused" Stroke="{StaticResource ComboBoxFocusedBorderBrush}" StrokeThickness="1" Visibility="Collapsed" Grid.ColumnSpan="2" />
											<Rectangle x:Name="disabled" Fill="{StaticResource ComboBoxDisabledBackgroundBrush}" Visibility="Collapsed" Grid.ColumnSpan="2" />
										</Grid>
										<ControlTemplate.Triggers>
											<Trigger Property="HasItems" Value="false">
												<Setter Property="Height" TargetName="DropDownBorder" Value="95" />
											</Trigger>
											<Trigger Property="IsEnabled" Value="false">
												<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
												<Setter Property="Background" Value="{StaticResource ComboBoxBackgroundBrush}" />
											</Trigger>
											<Trigger Property="IsGrouping" Value="true">
												<Setter Property="ScrollViewer.CanContentScroll" Value="false" />
											</Trigger>
											<Trigger Property="ScrollViewer.CanContentScroll" SourceName="DropDownScrollViewer" Value="false">
												<Setter Property="Canvas.Top" TargetName="OpaqueRect" Value="{Binding VerticalOffset, ElementName=DropDownScrollViewer}" />
												<Setter Property="Canvas.Left" TargetName="OpaqueRect" Value="{Binding HorizontalOffset, ElementName=DropDownScrollViewer}" />
											</Trigger>
										</ControlTemplate.Triggers>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
							<Style.Triggers>
								<Trigger Property="IsEditable" Value="true">
									<Setter Property="IsTabStop" Value="false" />
									<Setter Property="Padding" Value="0" />
									<Setter Property="Template" Value="{StaticResource ComboBoxEditableTemplate}" />
								</Trigger>
							</Style.Triggers>
						</Style>
						<Style x:Key="TextBoxStyle" TargetType="TextBox">
							<Setter Property="BorderThickness" Value="1" />
							<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
							<Setter Property="FontSize" Value="14.667" />
							<Setter Property="FontFamily" Value="Segoe UI" />
							<Setter Property="Background" Value="{StaticResource TextBoxBackgroundBrush}" />
							<Setter Property="BorderBrush" Value="{StaticResource TextBoxBorderBrush}" />
							<Setter Property="MinHeight" Value="30" />
							<Setter Property="Padding" Value="6,3" />
							<Setter Property="SelectionBrush" Value="{StaticResource TextBoxFocusedBrush}" />
							<Setter Property="Validation.ErrorTemplate" Value="{StaticResource TextBoxValidationToolTipTemplate}"/>
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="TextBox">
										<Grid x:Name="RootElement" SnapsToDevicePixels="True">
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="CommonStates">
													<VisualState x:Name="Normal" />
													<VisualState x:Name="MouseOver">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="BorderBrush" Storyboard.TargetName="Border">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource TextBoxHoverBorderBrush}" />
															</ObjectAnimationUsingKeyFrames>
															<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Background" Storyboard.TargetName="Border">
																<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource TextBoxHoverBackgroundBrush}" />
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Disabled">
														<Storyboard>
															<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="DisabledVisualElement" />
														</Storyboard>
													</VisualState>
													<VisualState x:Name="ReadOnly">
														<Storyboard>
															<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="ReadOnlyVisualElement" />
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
												<VisualStateGroup x:Name="FocusStates">
													<VisualState x:Name="Focused">
														<Storyboard>
															<DoubleAnimation Duration="0" To="1" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="FocusVisualElement" />
														</Storyboard>
													</VisualState>
													<VisualState x:Name="Unfocused">
														<Storyboard>
															<DoubleAnimation Duration="0" To="0" Storyboard.TargetProperty="Opacity" Storyboard.TargetName="FocusVisualElement" />
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
												<VisualStateGroup x:Name="ValidationStates">
													<VisualState x:Name="Valid" />
													<VisualState x:Name="InvalidUnfocused">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Visibility" Storyboard.TargetName="ValidationErrorElement">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="InvalidFocused">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Visibility" Storyboard.TargetName="ValidationErrorElement">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="IsOpen" Storyboard.TargetName="validationTooltip">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<System:Boolean>True</System:Boolean>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Border x:Name="Border" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" Opacity="1">
												<Grid>
													<Border x:Name="ReadOnlyVisualElement" Background="{StaticResource TextBoxReadOnlyBackgroundBrush}" Opacity="0" />
													<ScrollViewer x:Name="PART_ContentHost" BorderThickness="0" IsTabStop="False" Padding="{TemplateBinding Padding}" />
												</Grid>
											</Border>
											<Border x:Name="DisabledVisualElement" BorderBrush="{StaticResource DisabledVisualElement}" BorderThickness="{TemplateBinding BorderThickness}" Background="{StaticResource DisabledVisualElement}" IsHitTestVisible="False" Opacity="0" />
											<Border x:Name="FocusVisualElement" BorderBrush="{StaticResource TextBoxFocusedBrush}" BorderThickness="{TemplateBinding BorderThickness}" IsHitTestVisible="False" Opacity="0" />
											<Border x:Name="ValidationErrorElement" BorderBrush="{StaticResource ValidationErrorElement}" BorderThickness="{TemplateBinding BorderThickness}" Visibility="Collapsed">
												<ToolTipService.ToolTip>
													<ToolTip x:Name="validationTooltip" DataContext="{Binding RelativeSource={RelativeSource TemplatedParent}}" Placement="Right" PlacementTarget="{Binding RelativeSource={RelativeSource TemplatedParent}}" Template="{StaticResource TextBoxValidationToolTipTemplate}"/>
												</ToolTipService.ToolTip>
												<Grid Background="Transparent" HorizontalAlignment="Right" Height="12" Margin="1,-4,-4,0" VerticalAlignment="Top" Width="12">
													<Path Data="M 1,0 L6,0 A 2,2 90 0 1 8,2 L8,7 z" Fill="{StaticResource ValidationErrorElement}" Margin="1,3,0,0" />
													<Path Data="M 0,0 L2,0 L 8,6 L8,8" Fill="{StaticResource LightForegroundBrush}" Margin="1,3,0,0" />
												</Grid>
											</Border>
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
						<Style x:Key="ListBoxStyle" TargetType="ListBox">
							<Setter Property="Padding" Value="0" />
							<Setter Property="Background" Value="{StaticResource ListBoxBackgroundBrush}" />
							<Setter Property="BorderBrush" Value="{StaticResource ListBoxBorderBrush}" />
							<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
							<Setter Property="HorizontalContentAlignment" Value="Left" />
							<Setter Property="VerticalContentAlignment" Value="Top" />
							<Setter Property="IsTabStop" Value="False" />
							<Setter Property="BorderThickness" Value="1" />
							<Setter Property="ItemContainerStyle" Value="{StaticResource ListBoxItemStyle}" />
							<Setter Property="ScrollViewer.HorizontalScrollBarVisibility" Value="Auto" />
							<Setter Property="ScrollViewer.VerticalScrollBarVisibility" Value="Auto" />
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="ListBox">
										<Grid>
											<VisualStateManager.VisualStateGroups>
												<VisualStateGroup x:Name="ValidationStates">
													<VisualState x:Name="Valid" />
													<VisualState x:Name="InvalidUnfocused">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Visibility" Storyboard.TargetName="ValidationErrorElement">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
													<VisualState x:Name="InvalidFocused">
														<Storyboard>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="Visibility" Storyboard.TargetName="ValidationErrorElement">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<Visibility>Visible</Visibility>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
															<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="IsOpen" Storyboard.TargetName="validationTooltip">
																<DiscreteObjectKeyFrame KeyTime="0">
																	<DiscreteObjectKeyFrame.Value>
																		<System:Boolean>True</System:Boolean>
																	</DiscreteObjectKeyFrame.Value>
																</DiscreteObjectKeyFrame>
															</ObjectAnimationUsingKeyFrames>
														</Storyboard>
													</VisualState>
												</VisualStateGroup>
											</VisualStateManager.VisualStateGroups>
											<Border BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" Background="{TemplateBinding Background}">
												<ScrollViewer x:Name="ScrollViewer" BorderThickness="0" Padding="{TemplateBinding Padding}" Style="{StaticResource ScrollViewerStyle}">
													<ItemsPresenter />
												</ScrollViewer>
											</Border>
											<Border x:Name="ValidationErrorElement" BorderBrush="{StaticResource ValidationErrorElement}" BorderThickness="{TemplateBinding BorderThickness}" CornerRadius="2" Visibility="Collapsed">
												<ToolTipService.ToolTip>
													<ToolTip x:Name="validationTooltip" DataContext="{Binding RelativeSource={RelativeSource TemplatedParent}}" Placement="Right" PlacementTarget="{Binding RelativeSource={RelativeSource TemplatedParent}}" Template="{StaticResource ValidationToolTipTemplate}">
														<ToolTip.Triggers>
															<EventTrigger RoutedEvent="Canvas.Loaded">
																<BeginStoryboard>
																	<Storyboard>
																		<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="IsHitTestVisible" Storyboard.TargetName="validationTooltip">
																			<DiscreteObjectKeyFrame KeyTime="0">
																				<DiscreteObjectKeyFrame.Value>
																					<System:Boolean>true</System:Boolean>
																				</DiscreteObjectKeyFrame.Value>
																			</DiscreteObjectKeyFrame>
																		</ObjectAnimationUsingKeyFrames>
																	</Storyboard>
																</BeginStoryboard>
															</EventTrigger>
														</ToolTip.Triggers>
													</ToolTip>
												</ToolTipService.ToolTip>
												<Grid Background="{StaticResource TransparentBrush}" HorizontalAlignment="Right" Height="10" Margin="0,-4,-4,0" VerticalAlignment="Top" Width="10">
													<Path Data="M 1,0 L6,0 A 2,2 90 0 1 8,2 L8,7 z" Fill="{StaticResource ValidationErrorElement}" Margin="-1,3,0,0" />
													<Path Data="M 0,0 L2,0 L 8,6 L8,8" Fill="{StaticResource LightForegroundBrush}" Margin="-1,3,0,0" />
												</Grid>
											</Border>
										</Grid>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Style>
					</ResourceDictionary>
				</ResourceDictionary.MergedDictionaries>
				<SolidColorBrush x:Key="SliderThumbBackgroundBrush" Color="{StaticResource Color_003}" />
				<SolidColorBrush x:Key="SliderThumbHoverBackgroundBrush" Color="{StaticResource Color_002}" />
				<SolidColorBrush x:Key="SliderThumbPressedBackgroundBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="SliderThumbDisabledBackgroundBrush" Color="{StaticResource Color_005}" />
				<SolidColorBrush x:Key="SliderTrackDisabledOverlayBackgroundBrush" Color="{StaticResource Color_008}" />
				<SolidColorBrush x:Key="SliderThumbFocusedBorderBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="SliderTrackBackgroundBrush" Color="{StaticResource Color_005}" />
				<SolidColorBrush x:Key="SliderSelectionRangeBackgroundBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="GridSplitterBackgroundBrush" Color="{StaticResource Color_008}" />
				<SolidColorBrush x:Key="GridSplitterBorderBrush" Color="{StaticResource Color_004}" />
				<SolidColorBrush x:Key="GridSplitterHoverBackgroundBrush" Color="{StaticResource Color_006}" />
				<SolidColorBrush x:Key="GridSplitterHoverBorderBrush" Color="{StaticResource Color_003}" />
				<SolidColorBrush x:Key="GridSplitterPressedBackgroundBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="GridSplitterFocusedBorderBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="ProgressBarBackgroundBrush" Color="{StaticResource Color_005}" />
				<SolidColorBrush x:Key="ProgressBarForegroundBrush" Color="{StaticResource Color_024}" />
				<LinearGradientBrush x:Key="ProgressBarIndeterminateBackgroundBrush" EndPoint="0,1" MappingMode="Absolute" SpreadMethod="Repeat" StartPoint="20,1" Opacity="0.8">
					<LinearGradientBrush.Transform>
						<TransformGroup>
							<TranslateTransform X="0" />
							<SkewTransform AngleX="-30" />
						</TransformGroup>
					</LinearGradientBrush.Transform>
					<GradientStop Color="{StaticResource Color_023}" Offset="0.249" />
					<GradientStop Color="{StaticResource Color_024}" Offset=".25" />
					<GradientStop Color="{StaticResource Color_024}" Offset="0.75" />
					<GradientStop Color="{StaticResource Color_023}" Offset="0.751" />
				</LinearGradientBrush>
				<SolidColorBrush x:Key="TooltipBackgroundBrush" Color="{StaticResource Color_009}" />
				<SolidColorBrush x:Key="TooltipBorderBrush" Color="{StaticResource Color_004}" />
				<SolidColorBrush x:Key="ExpanderButtonBackgroundBrush" Color="{StaticResource Color_009}" />
				<SolidColorBrush x:Key="ExpanderButtonBorderBrush" Color="{StaticResource Color_004}" />
				<SolidColorBrush x:Key="ExpanderButtonHoverBackgroundBrush" Color="{StaticResource Color_007}" />
				<SolidColorBrush x:Key="ExpanderButtonHoverBorderBrush" Color="{StaticResource Color_003}" />
				<SolidColorBrush x:Key="ExpanderButtonPressedBackgroundBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="ExpanderButtonPressedBorderBrush" Color="{StaticResource Color_024}" />
				<SolidColorBrush x:Key="ExpanderArrowHoverBorderBrush" Color="{StaticResource Color_002}" />
				<SolidColorBrush x:Key="ExpanderArrowPressedBorderBrush" Color="{StaticResource Color_009}" />
				<SolidColorBrush x:Key="ExpanderDisabledForegroundBrush" Color="{StaticResource Color_007}" />
				<SolidColorBrush x:Key="ExpanderDisabledBackgroundBrush" Color="{StaticResource Color_007}" />
				<SolidColorBrush x:Key="GroupBoxBorderBrush" Color="{StaticResource Color_003}" />
				<SolidColorBrush x:Key="PasswordBoxForegroundBrush" Color="{StaticResource Color_024}" />
				<Style x:Key="TextBlockStyle" TargetType="TextBlock">
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="FontSize" Value="13.333" />
					<Setter Property="FontFamily" Value="Segoe UI" />
				</Style>
				<Style x:Key="LabelStyle" TargetType="{x:Type Label}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="13.333" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="IsTabStop" Value="False" />
					<Setter Property="HorizontalContentAlignment" Value="Left" />
				</Style>
				<Style x:Key="SliderRepeatButtonStyle" TargetType="{x:Type RepeatButton}">
					<Setter Property="OverridesDefaultStyle" Value="true" />
					<Setter Property="Focusable" Value="false" />
					<Setter Property="IsTabStop" Value="false" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type RepeatButton}">
								<Rectangle Fill="{StaticResource TransparentBrush}" />
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="HSliderThumbStyle" TargetType="{x:Type Thumb}">
					<Setter Property="Background" Value="{StaticResource SliderThumbBackgroundBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="MinHeight" Value="12" />
					<Setter Property="MinWidth" Value="8" />
					<Setter Property="IsTabStop" Value="False" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type Thumb}">
								<Grid>
									<Ellipse x:Name="ThumbBackground" Fill="{TemplateBinding Background}" Width="16" Height="16" />
									<Ellipse x:Name="FocusedVisualElement" Stroke="{StaticResource SliderThumbFocusedBorderBrush}" Width="16" Height="16" StrokeThickness="2" Opacity="0" />
									<Ellipse x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Width="16" Height="16" Opacity="0" />
								</Grid>
								<ControlTemplate.Triggers>
									<Trigger Property="IsMouseOver" Value="True">
										<Setter TargetName="ThumbBackground" Property="Fill" Value="{StaticResource SliderThumbHoverBackgroundBrush}" />
									</Trigger>
									<Trigger Property="IsMouseCaptured" Value="True">
										<Setter TargetName="ThumbBackground" Property="Fill" Value="{StaticResource SliderThumbPressedBackgroundBrush}" />
									</Trigger>
									<Trigger Property="IsEnabled" Value="false">
										<Setter TargetName="DisabledVisualElement" Property="Opacity" Value="1" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="VSliderThumbStyle" TargetType="{x:Type Thumb}">
					<Setter Property="Background" Value="{StaticResource SliderThumbBackgroundBrush}" />
					<Setter Property="MinHeight" Value="8" />
					<Setter Property="MinWidth" Value="12" />
					<Setter Property="IsTabStop" Value="False" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type Thumb}">
								<Grid>
									<Ellipse x:Name="ThumbBackground" Fill="{TemplateBinding Background}" Width="16" Height="16" />
									<Ellipse x:Name="FocusedVisualElement" Stroke="{StaticResource SliderThumbFocusedBorderBrush}" Width="16" Height="16" StrokeThickness="2" Opacity="0" />
									<Ellipse x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Width="16" Height="16" Opacity="0" />
								</Grid>
								<ControlTemplate.Triggers>
									<Trigger Property="IsMouseOver" Value="True">
										<Setter TargetName="ThumbBackground" Property="Fill" Value="{StaticResource SliderThumbHoverBackgroundBrush}" />
									</Trigger>
									<Trigger Property="IsMouseCaptured" Value="True">
										<Setter TargetName="ThumbBackground" Property="Fill" Value="{StaticResource SliderThumbPressedBackgroundBrush}" />
									</Trigger>
									<Trigger Property="IsEnabled" Value="false">
										<Setter TargetName="DisabledVisualElement" Property="Opacity" Value="1" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="SliderStyle" TargetType="{x:Type Slider}">
					<Setter Property="Background" Value="Transparent" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="Stylus.IsPressAndHoldEnabled" Value="false" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type Slider}">
								<Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" SnapsToDevicePixels="true">
									<VisualStateManager.VisualStateGroups>
										<VisualStateGroup x:Name="CommonStates">
											<VisualState x:Name="Normal" />
											<VisualState x:Name="MouseOver" />
											<VisualState x:Name="Disabled" />
										</VisualStateGroup>
									</VisualStateManager.VisualStateGroups>
									<Grid>
										<Grid.RowDefinitions>
											<RowDefinition Height="Auto" />
											<RowDefinition Height="Auto" MinHeight="{TemplateBinding MinHeight}" />
											<RowDefinition Height="Auto" />
										</Grid.RowDefinitions>
										<TickBar x:Name="TopTick" Fill="{TemplateBinding Foreground}" Height="6" Placement="Top" Grid.Row="0" Visibility="Collapsed" />
										<TickBar x:Name="BottomTick" Fill="{TemplateBinding Foreground}" Height="6" Placement="Bottom" Grid.Row="2" Visibility="Collapsed" />
										<Border x:Name="TrackBackground" Background="{StaticResource SliderTrackBackgroundBrush}" Height="6" Grid.Row="1" VerticalAlignment="center">
											<Canvas Margin="-6,-1">
												<Rectangle x:Name="PART_SelectionRange" Fill="{StaticResource SliderSelectionRangeBackgroundBrush}" Height="6" Width="0" Visibility="Hidden" />
											</Canvas>
										</Border>
										<Track x:Name="PART_Track" Grid.Row="1">
											<Track.DecreaseRepeatButton>
												<RepeatButton Command="{x:Static Slider.DecreaseLarge}" Style="{StaticResource SliderRepeatButtonStyle}" />
											</Track.DecreaseRepeatButton>
											<Track.IncreaseRepeatButton>
												<RepeatButton Command="{x:Static Slider.IncreaseLarge}" Style="{StaticResource SliderRepeatButtonStyle}" />
											</Track.IncreaseRepeatButton>
											<Track.Thumb>
												<Thumb x:Name="Thumb" Style="{StaticResource HSliderThumbStyle}" />
											</Track.Thumb>
										</Track>
									</Grid>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="TickPlacement" Value="TopLeft">
										<Setter Property="Visibility" TargetName="TopTick" Value="Visible" />
										<Setter Property="Style" TargetName="Thumb" Value="{StaticResource HSliderThumbStyle}" />
										<Setter Property="Margin" TargetName="TrackBackground" Value="5,2,5,0" />
									</Trigger>
									<Trigger Property="TickPlacement" Value="BottomRight">
										<Setter Property="Visibility" TargetName="BottomTick" Value="Visible" />
										<Setter Property="Style" TargetName="Thumb" Value="{StaticResource HSliderThumbStyle}" />
										<Setter Property="Margin" TargetName="TrackBackground" Value="5,0,5,2" />
									</Trigger>
									<Trigger Property="TickPlacement" Value="Both">
										<Setter Property="Visibility" TargetName="TopTick" Value="Visible" />
										<Setter Property="Visibility" TargetName="BottomTick" Value="Visible" />
									</Trigger>
									<Trigger Property="IsSelectionRangeEnabled" Value="true">
										<Setter Property="Visibility" TargetName="PART_SelectionRange" Value="Visible" />
									</Trigger>
									<Trigger Property="IsKeyboardFocused" Value="true">
										<Setter Property="Foreground" TargetName="Thumb" Value="{StaticResource SliderThumbFocusedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
					<Style.Triggers>
						<Trigger Property="Orientation" Value="Vertical">
							<Setter Property="Template">
								<Setter.Value>
									<ControlTemplate TargetType="{x:Type Slider}">
										<Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" SnapsToDevicePixels="true">
											<Grid>
												<Grid.ColumnDefinitions>
													<ColumnDefinition Width="Auto" />
													<ColumnDefinition MinWidth="{TemplateBinding MinWidth}" Width="Auto" />
													<ColumnDefinition Width="Auto" />
												</Grid.ColumnDefinitions>
												<TickBar x:Name="TopTick" Grid.Column="0" Fill="{TemplateBinding Foreground}" Placement="Left" Visibility="Collapsed" Width="6" />
												<TickBar x:Name="BottomTick" Grid.Column="2" Fill="{TemplateBinding Foreground}" Placement="Right" Visibility="Collapsed" Width="6" />
												<Border x:Name="TrackBackground" Background="{StaticResource SliderTrackBackgroundBrush}" Grid.Column="1" HorizontalAlignment="center" Width="6">
													<Canvas Margin="-1,-6">
														<Rectangle x:Name="PART_SelectionRange" Fill="{StaticResource SliderSelectionRangeBackgroundBrush}" Visibility="Hidden" Width="6" />
													</Canvas>
												</Border>
												<Track x:Name="PART_Track" Grid.Column="1">
													<Track.DecreaseRepeatButton>
														<RepeatButton Command="{x:Static Slider.DecreaseLarge}" Style="{StaticResource SliderRepeatButtonStyle}" />
													</Track.DecreaseRepeatButton>
													<Track.IncreaseRepeatButton>
														<RepeatButton Command="{x:Static Slider.IncreaseLarge}" Style="{StaticResource SliderRepeatButtonStyle}" />
													</Track.IncreaseRepeatButton>
													<Track.Thumb>
														<Thumb x:Name="Thumb" Style="{StaticResource VSliderThumbStyle}" />
													</Track.Thumb>
												</Track>
											</Grid>
										</Border>
										<ControlTemplate.Triggers>
											<Trigger Property="TickPlacement" Value="TopLeft">
												<Setter Property="Visibility" TargetName="TopTick" Value="Visible" />
												<Setter Property="Style" TargetName="Thumb" Value="{StaticResource VSliderThumbStyle}" />
												<Setter Property="Margin" TargetName="TrackBackground" Value="2,5,0,5" />
											</Trigger>
											<Trigger Property="TickPlacement" Value="BottomRight">
												<Setter Property="Visibility" TargetName="BottomTick" Value="Visible" />
												<Setter Property="Style" TargetName="Thumb" Value="{StaticResource VSliderThumbStyle}" />
												<Setter Property="Margin" TargetName="TrackBackground" Value="0,5,2,5" />
											</Trigger>
											<Trigger Property="TickPlacement" Value="Both">
												<Setter Property="Visibility" TargetName="TopTick" Value="Visible" />
												<Setter Property="Visibility" TargetName="BottomTick" Value="Visible" />
											</Trigger>
											<Trigger Property="IsSelectionRangeEnabled" Value="true">
												<Setter Property="Visibility" TargetName="PART_SelectionRange" Value="Visible" />
											</Trigger>
											<Trigger Property="IsKeyboardFocused" Value="true">
												<Setter Property="Foreground" TargetName="Thumb" Value="{StaticResource SliderThumbFocusedBorderBrush}" />
											</Trigger>
										</ControlTemplate.Triggers>
									</ControlTemplate>
								</Setter.Value>
							</Setter>
						</Trigger>
					</Style.Triggers>
				</Style>
				<Style x:Key="RepeatButtonStyle" TargetType="{x:Type RepeatButton}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="14.667" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="Padding" Value="10,0,10,2" />
					<Setter Property="MinHeight" Value="30" />
					<Setter Property="MinWidth" Value="30" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type RepeatButton}">
								<Grid SnapsToDevicePixels="True">
									<VisualStateManager.VisualStateGroups>
										<VisualStateGroup x:Name="CommonStates">
											<VisualState x:Name="Normal" />
											<VisualState x:Name="MouseOver">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBackgroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBorderBrush}" />
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Pressed">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBackgroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBorderBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Foreground" Storyboard.TargetName="ContentControl">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource LightForegroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Disabled">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="DisabledVisualElement">
														<DiscreteObjectKeyFrame KeyTime="0">
															<DiscreteObjectKeyFrame.Value>
																<Visibility>Visible</Visibility>
															</DiscreteObjectKeyFrame.Value>
														</DiscreteObjectKeyFrame>
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
										</VisualStateGroup>
										<VisualStateGroup x:Name="FocusStates">
											<VisualState x:Name="Focused">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="FocusedVisualElement">
														<DiscreteObjectKeyFrame KeyTime="0">
															<DiscreteObjectKeyFrame.Value>
																<Visibility>Visible</Visibility>
															</DiscreteObjectKeyFrame.Value>
														</DiscreteObjectKeyFrame>
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Unfocused" />
										</VisualStateGroup>
									</VisualStateManager.VisualStateGroups>
									<Rectangle x:Name="Bd" Fill="{StaticResource ButtonBackgroundBrush}" Stroke="{StaticResource ButtonBorderBrush}" StrokeThickness="1" />
									<ContentControl x:Name="ContentControl" Foreground="{TemplateBinding Foreground}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
										<ContentPresenter x:Name="contentPresenter" />
									</ContentControl>
									<Rectangle x:Name="FocusedVisualElement" Stroke="{StaticResource ButtonPressedBorderBrush}" Visibility="Collapsed" StrokeThickness="2" />
									<Rectangle x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Visibility="Collapsed" />
								</Grid>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="GridSplitterStyle" TargetType="{x:Type GridSplitter}">
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="Background" Value="{StaticResource GridSplitterBackgroundBrush}" />
					<Setter Property="BorderBrush" Value="{StaticResource GridSplitterBorderBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="SnapsToDevicePixels" Value="True" />
					<Setter Property="PreviewStyle">
						<Setter.Value>
							<Style TargetType="Control">
								<Setter Property="Control.Template">
									<Setter.Value>
										<ControlTemplate>
											<Rectangle Fill="{StaticResource GridSplitterPressedBackgroundBrush}" Opacity="0.8" />
										</ControlTemplate>
									</Setter.Value>
								</Setter>
							</Style>
						</Setter.Value>
					</Setter>
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate>
								<Grid>
									<Border x:Name="border" BorderThickness="{TemplateBinding BorderThickness}" BorderBrush="{TemplateBinding BorderBrush}" Background="{TemplateBinding Background}" MinHeight="8" MinWidth="8">
										<Grid>
											<StackPanel x:Name="HGrip" Height="8" VerticalAlignment="Center" HorizontalAlignment="Center" Orientation="Vertical">
												<Rectangle Fill="{StaticResource GlyphBackgroundBrush}" Height="1" Margin="1,2,1,1" StrokeThickness="0" Width="20" />
												<Rectangle Fill="{StaticResource GlyphBackgroundBrush}" Height="1" Margin="1,1,1,2" StrokeThickness="0" Width="20" />
											</StackPanel>
											<StackPanel x:Name="VGrip" Width="8" VerticalAlignment="Center" HorizontalAlignment="Center" Orientation="Horizontal" Visibility="Collapsed">
												<Rectangle Fill="{StaticResource GlyphBackgroundBrush}" Height="20" Margin="2,1,1,1" StrokeThickness="0" Width="1" />
												<Rectangle Fill="{StaticResource GlyphBackgroundBrush}" Height="20" Margin="1,1,2,1" StrokeThickness="0" Width="1" />
											</StackPanel>
										</Grid>
									</Border>
								</Grid>
								<ControlTemplate.Triggers>
									<Trigger Property="HorizontalAlignment" Value="Stretch">
										<Setter TargetName="HGrip" Property="Visibility" Value="Visible" />
										<Setter TargetName="VGrip" Property="Visibility" Value="Collapsed" />
									</Trigger>
									<Trigger Property="VerticalAlignment" Value="Stretch">
										<Setter TargetName="VGrip" Property="Visibility" Value="Visible" />
										<Setter TargetName="HGrip" Property="Visibility" Value="Collapsed" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="True">
										<Setter TargetName="border" Property="Background" Value="{StaticResource GridSplitterHoverBackgroundBrush}" />
										<Setter TargetName="border" Property="BorderBrush" Value="{StaticResource GridSplitterHoverBorderBrush}" />
									</Trigger>
									<Trigger Property="IsFocused" Value="True">
										<Setter TargetName="border" Property="BorderBrush" Value="{StaticResource GridSplitterFocusedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ProgressBarStyle" TargetType="{x:Type ProgressBar}">
					<Setter Property="Foreground" Value="{StaticResource ProgressBarForegroundBrush}" />
					<Setter Property="Background" Value="{StaticResource ProgressBarBackgroundBrush}" />
					<Setter Property="BorderThickness" Value="0" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ProgressBar}">
								<Grid x:Name="TemplateRoot" SnapsToDevicePixels="true">
									<VisualStateManager.VisualStateGroups>
										<VisualStateGroup x:Name="CommonStates">
											<VisualState x:Name="Determinate" />
											<VisualState x:Name="Indeterminate">
												<Storyboard RepeatBehavior="Forever">
													<DoubleAnimation Duration="00:00:.5" From="0" To="20" Storyboard.TargetProperty="(Shape.Fill).(LinearGradientBrush.Transform).(TransformGroup.Children)[0].X" Storyboard.TargetName="IndeterminateGradientFill" />
												</Storyboard>
											</VisualState>
										</VisualStateGroup>
									</VisualStateManager.VisualStateGroups>
									<Border x:Name="ProgressBarTrack" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" />
									<Rectangle x:Name="PART_Track" Margin="{TemplateBinding BorderThickness}" />
									<Decorator x:Name="PART_Indicator" HorizontalAlignment="Left" Margin="{TemplateBinding BorderThickness}">
										<Grid x:Name="Foreground">
											<Rectangle x:Name="Indicator" Fill="{TemplateBinding Foreground}" />
										</Grid>
									</Decorator>
									<Grid x:Name="IndeterminateRoot" Visibility="Collapsed">
										<Rectangle x:Name="IndeterminateSolidFill" Fill="{TemplateBinding Foreground}" Margin="{TemplateBinding BorderThickness}" Opacity="1" RenderTransformOrigin="0.5,0.5" StrokeThickness="0" />
										<Rectangle x:Name="IndeterminateGradientFill" Fill="{StaticResource ProgressBarIndeterminateBackgroundBrush}" Margin="{TemplateBinding BorderThickness}" StrokeThickness="1" />
									</Grid>
								</Grid>
								<ControlTemplate.Triggers>
									<Trigger Property="Orientation" Value="Vertical">
										<Setter Property="LayoutTransform" TargetName="TemplateRoot">
											<Setter.Value>
												<RotateTransform Angle="-90" />
											</Setter.Value>
										</Setter>
									</Trigger>
									<Trigger Property="IsIndeterminate" Value="true">
										<Setter Property="Visibility" TargetName="Indicator" Value="Collapsed" />
										<Setter Property="Visibility" TargetName="IndeterminateRoot" Value="Visible" />
									</Trigger>
									<Trigger Property="IsIndeterminate" Value="false"/>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="PasswordBoxStyle" TargetType="{x:Type PasswordBox}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="13.333" />
					<Setter Property="Foreground" Value="{StaticResource PasswordBoxForegroundBrush}" />
					<Setter Property="Background" Value="{StaticResource TextBoxBackgroundBrush}" />
					<Setter Property="BorderBrush" Value="{StaticResource TextBoxBorderBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="Padding" Value="6,4" />
					<Setter Property="MinHeight" Value="30" />
					<Setter Property="SelectionBrush" Value="{StaticResource TextBoxFocusedBrush}" />
					<Setter Property="PasswordChar" Value="*" />
					<Setter Property="KeyboardNavigation.TabNavigation" Value="None" />
					<Setter Property="AllowDrop" Value="true" />
					<Setter Property="FocusVisualStyle" Value="{x:Null}" />
					<Setter Property="ScrollViewer.PanningMode" Value="VerticalFirst" />
					<Setter Property="Stylus.IsFlicksEnabled" Value="False" />
					<Setter Property="FlowDirection" Value="LeftToRight" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type PasswordBox}">
								<Grid>
									<Border Background="{TemplateBinding Background}" x:Name="Bd" BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" />
									<Border x:Name="DisabledVisualElement" BorderBrush="{StaticResource DisabledVisualElement}" BorderThickness="{TemplateBinding BorderThickness}" Background="{StaticResource DisabledVisualElement}" IsHitTestVisible="False" Opacity="0" />
									<Border x:Name="ReadOnlyVisualElement" Background="{StaticResource TextBoxReadOnlyBackgroundBrush}" Opacity="0" />
									<Border>
										<ScrollViewer x:Name="PART_ContentHost" />
									</Border>
								</Grid>
								<ControlTemplate.Triggers>
									<Trigger Property="IsEnabled" Value="False">
										<Setter Property="Opacity" Value="1" TargetName="DisabledVisualElement" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="True">
										<Setter Property="BorderBrush" Value="{StaticResource TextBoxHoverBorderBrush}" TargetName="Bd" />
									</Trigger>
									<Trigger Property="IsFocused" Value="True">
										<Setter Property="BorderBrush" Value="{StaticResource TextBoxFocusedBrush}" TargetName="Bd" />
									</Trigger>
									<MultiDataTrigger>
										<MultiDataTrigger.Conditions>
											<Condition Binding="{Binding IsReadOnly, RelativeSource={RelativeSource Self}}" Value="True" />
											<Condition Binding="{Binding IsEnabled, RelativeSource={RelativeSource Self}}" Value="True" />
										</MultiDataTrigger.Conditions>
										<Setter Property="Opacity" Value="1" TargetName="ReadOnlyVisualElement" />
									</MultiDataTrigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="{x:Type ToolTip}" TargetType="ToolTip">
					<Setter Property="OverridesDefaultStyle" Value="true" />
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="14.667" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="Background" Value="{StaticResource TooltipBackgroundBrush}" />
					<Setter Property="BorderBrush" Value="{StaticResource TooltipBorderBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="Padding" Value="10,7" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="ToolTip">
								<Grid>
									<Rectangle Stroke="{TemplateBinding BorderBrush}" Fill="{TemplateBinding Background}" StrokeThickness="{TemplateBinding BorderThickness}" />
									<StackPanel Orientation="Horizontal" d:LayoutOverrides="Width, Height">
										<ContentPresenter Margin="{TemplateBinding Padding}" Content="{TemplateBinding Content}" />
									</StackPanel>
								</Grid>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ExpanderRightHeaderStyle" TargetType="{x:Type ToggleButton}">
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ToggleButton}">
								<Border Padding="{TemplateBinding Padding}">
									<Grid Background="{StaticResource TransparentBrush}" SnapsToDevicePixels="False">
										<Grid.RowDefinitions>
											<RowDefinition Height="30" />
											<RowDefinition Height="*" />
										</Grid.RowDefinitions>
										<Grid>
											<Grid.LayoutTransform>
												<TransformGroup>
													<TransformGroup.Children>
														<TransformCollection>
															<RotateTransform Angle="-90" />
														</TransformCollection>
													</TransformGroup.Children>
												</TransformGroup>
											</Grid.LayoutTransform>
											<Rectangle x:Name="rectangle" Width="30" Height="30" Fill="{StaticResource ExpanderButtonBackgroundBrush}" HorizontalAlignment="Center" Stroke="{StaticResource ExpanderButtonBorderBrush}" VerticalAlignment="Center" />
											<Path x:Name="arrow" Width="10" Height="6" Fill="{StaticResource GlyphBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" RenderTransformOrigin="0.5, 0.5" />
										</Grid>
										<ContentPresenter HorizontalAlignment="Center" Margin="0,4,0,0" Grid.Row="1" RecognizesAccessKey="True" SnapsToDevicePixels="True" VerticalAlignment="Stretch" />
									</Grid>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="IsChecked" Value="true">
										<Setter Property="Data" TargetName="arrow" Value="M3.4,-4.4 L6.8,3.9 3.9566912E-07,3.9 z" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowHoverBorderBrush}" />
									</Trigger>
									<Trigger Property="IsPressed" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowPressedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ExpanderUpHeaderStyle" TargetType="{x:Type ToggleButton}">
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ToggleButton}">
								<Border Padding="{TemplateBinding Padding}">
									<Grid Background="{StaticResource TransparentBrush}" SnapsToDevicePixels="False">
										<Grid.ColumnDefinitions>
											<ColumnDefinition Width="30" />
											<ColumnDefinition Width="*" />
										</Grid.ColumnDefinitions>
										<Grid>
											<Grid.LayoutTransform>
												<TransformGroup>
													<TransformGroup.Children>
														<TransformCollection>
															<RotateTransform Angle="180" />
														</TransformCollection>
													</TransformGroup.Children>
												</TransformGroup>
											</Grid.LayoutTransform>
											<Rectangle x:Name="rectangle" Width="30" Height="30" Fill="{StaticResource ExpanderButtonBackgroundBrush}" HorizontalAlignment="Center" Stroke="{StaticResource ExpanderButtonBorderBrush}" VerticalAlignment="Center" />
											<Path x:Name="arrow" Width="10" Height="6" Fill="{StaticResource GlyphBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" RenderTransformOrigin="0.5, 0.5" />
										</Grid>
										<ContentPresenter Grid.Column="1" HorizontalAlignment="Stretch" Margin="4,0,0,0" RecognizesAccessKey="True" SnapsToDevicePixels="True" VerticalAlignment="Center" />
									</Grid>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="IsChecked" Value="true">
										<Setter Property="Data" TargetName="arrow" Value="M3.4,-4.4 L6.8,3.9 3.9566912E-07,3.9 z" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowHoverBorderBrush}" />
									</Trigger>
									<Trigger Property="IsPressed" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowPressedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ExpanderLeftHeaderStyle" TargetType="{x:Type ToggleButton}">
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ToggleButton}">
								<Border Padding="{TemplateBinding Padding}">
									<Grid Background="{StaticResource TransparentBrush}" SnapsToDevicePixels="False">
										<Grid.RowDefinitions>
											<RowDefinition Height="30" />
											<RowDefinition Height="*" />
										</Grid.RowDefinitions>
										<Grid>
											<Grid.LayoutTransform>
												<TransformGroup>
													<TransformGroup.Children>
														<TransformCollection>
															<RotateTransform Angle="90" />
														</TransformCollection>
													</TransformGroup.Children>
												</TransformGroup>
											</Grid.LayoutTransform>
											<Rectangle x:Name="rectangle" Width="30" Height="30" Fill="{StaticResource ExpanderButtonBackgroundBrush}" HorizontalAlignment="Center" Stroke="{StaticResource ExpanderButtonBorderBrush}" VerticalAlignment="Center" />
											<Path x:Name="arrow" Width="10" Height="6" Fill="{StaticResource GlyphBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" RenderTransformOrigin="0.5, 0.5" />
										</Grid>
										<ContentPresenter Grid.Row="1" HorizontalAlignment="Center" Margin="0,4,0,0" RecognizesAccessKey="True" SnapsToDevicePixels="True" VerticalAlignment="Stretch" />
									</Grid>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="IsChecked" Value="true">
										<Setter Property="Data" TargetName="arrow" Value="M3.4,-4.4 L6.8,3.9 3.9566912E-07,3.9 z" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowHoverBorderBrush}" />
									</Trigger>
									<Trigger Property="IsPressed" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowPressedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ExpanderDownHeaderStyle" TargetType="{x:Type ToggleButton}">
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ToggleButton}">
								<Border Padding="{TemplateBinding Padding}">
									<Grid Background="{StaticResource TransparentBrush}" SnapsToDevicePixels="False">
										<Grid.ColumnDefinitions>
											<ColumnDefinition Width="30" />
											<ColumnDefinition Width="*" />
										</Grid.ColumnDefinitions>
										<Rectangle x:Name="rectangle" Width="30" Height="30" Fill="{StaticResource ExpanderButtonBackgroundBrush}" HorizontalAlignment="Center" Stroke="{StaticResource ExpanderButtonBorderBrush}" VerticalAlignment="Center" />
										<Path x:Name="arrow" Width="10" Height="6" Fill="{StaticResource GlyphBackgroundBrush}" Data="F1 M 301.14,-189.041L 311.57,-189.041L 306.355,-182.942L 301.14,-189.041 Z " Stretch="Fill" RenderTransformOrigin="0.5, 0.5" />
										<ContentPresenter Grid.Column="1" HorizontalAlignment="Stretch" Margin="4,0,0,0" RecognizesAccessKey="True" SnapsToDevicePixels="True" VerticalAlignment="Center" />
									</Grid>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="IsChecked" Value="true">
										<Setter Property="Data" TargetName="arrow" Value="M3.4,-4.4 L6.8,3.9 3.9566912E-07,3.9 z" />
									</Trigger>
									<Trigger Property="IsMouseOver" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonHoverBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowHoverBorderBrush}" />
									</Trigger>
									<Trigger Property="IsPressed" Value="true">
										<Setter Property="Fill" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBackgroundBrush}" />
										<Setter Property="Stroke" TargetName="rectangle" Value="{StaticResource ExpanderButtonPressedBorderBrush}" />
										<Setter Property="Fill" TargetName="arrow" Value="{StaticResource ExpanderArrowPressedBorderBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ExpanderStyle" TargetType="{x:Type Expander}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="14.667" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="HorizontalContentAlignment" Value="Stretch" />
					<Setter Property="VerticalContentAlignment" Value="Stretch" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type Expander}">
								<Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" CornerRadius="3" SnapsToDevicePixels="true">
									<DockPanel>
										<ToggleButton x:Name="HeaderSite" ContentTemplate="{TemplateBinding HeaderTemplate}" ContentTemplateSelector="{TemplateBinding HeaderTemplateSelector}" Content="{TemplateBinding Header}" DockPanel.Dock="Top" Foreground="{TemplateBinding Foreground}" FontWeight="{TemplateBinding FontWeight}" FontStyle="{TemplateBinding FontStyle}" FontStretch="{TemplateBinding FontStretch}" FontSize="{TemplateBinding FontSize}" FontFamily="{TemplateBinding FontFamily}" HorizontalContentAlignment="{TemplateBinding HorizontalContentAlignment}" IsChecked="{Binding IsExpanded, Mode=TwoWay, RelativeSource={RelativeSource TemplatedParent}}" Margin="1" MinWidth="0" MinHeight="0" Padding="{TemplateBinding Padding}" Style="{StaticResource ExpanderDownHeaderStyle}" VerticalContentAlignment="{TemplateBinding VerticalContentAlignment}" />
										<ContentPresenter x:Name="ExpandSite" DockPanel.Dock="Bottom" Focusable="false" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" Visibility="Collapsed" VerticalAlignment="{TemplateBinding VerticalContentAlignment}" />
									</DockPanel>
								</Border>
								<ControlTemplate.Triggers>
									<Trigger Property="IsExpanded" Value="true">
										<Setter Property="Visibility" TargetName="ExpandSite" Value="Visible" />
									</Trigger>
									<Trigger Property="ExpandDirection" Value="Right">
										<Setter Property="DockPanel.Dock" TargetName="ExpandSite" Value="Right" />
										<Setter Property="DockPanel.Dock" TargetName="HeaderSite" Value="Left" />
										<Setter Property="Style" TargetName="HeaderSite" Value="{StaticResource ExpanderRightHeaderStyle}" />
									</Trigger>
									<Trigger Property="ExpandDirection" Value="Up">
										<Setter Property="DockPanel.Dock" TargetName="ExpandSite" Value="Top" />
										<Setter Property="DockPanel.Dock" TargetName="HeaderSite" Value="Bottom" />
										<Setter Property="Style" TargetName="HeaderSite" Value="{StaticResource ExpanderUpHeaderStyle}" />
									</Trigger>
									<Trigger Property="ExpandDirection" Value="Left">
										<Setter Property="DockPanel.Dock" TargetName="ExpandSite" Value="Left" />
										<Setter Property="DockPanel.Dock" TargetName="HeaderSite" Value="Right" />
										<Setter Property="Style" TargetName="HeaderSite" Value="{StaticResource ExpanderLeftHeaderStyle}" />
									</Trigger>
									<Trigger Property="IsEnabled" Value="false">
										<Setter Property="Foreground" Value="{StaticResource ExpanderDisabledForegroundBrush}" />
									</Trigger>
								</ControlTemplate.Triggers>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style x:Key="ToggleButtonStyle" TargetType="{x:Type ToggleButton}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="14.667" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="Padding" Value="10,0,10,2" />
					<Setter Property="MinHeight" Value="30" />
					<Setter Property="MinWidth" Value="30" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type ToggleButton}">
								<Grid>
									<VisualStateManager.VisualStateGroups>
										<VisualStateGroup x:Name="CommonStates">
											<VisualState x:Name="Normal" />
											<VisualState x:Name="MouseOver">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBackgroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonHoverBorderBrush}" />
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Pressed">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Fill">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBackgroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetName="Bd" Storyboard.TargetProperty="Stroke">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource ButtonPressedBorderBrush}" />
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Foreground" Storyboard.TargetName="ContentControl">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource LightForegroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Disabled">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="DisabledVisualElement">
														<DiscreteObjectKeyFrame KeyTime="0">
															<DiscreteObjectKeyFrame.Value>
																<Visibility>Visible</Visibility>
															</DiscreteObjectKeyFrame.Value>
														</DiscreteObjectKeyFrame>
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
										</VisualStateGroup>
										<VisualStateGroup x:Name="CheckStates">
											<VisualState x:Name="Checked">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="checked">
														<DiscreteObjectKeyFrame KeyTime="0">
															<DiscreteObjectKeyFrame.Value>
																<Visibility>Visible</Visibility>
															</DiscreteObjectKeyFrame.Value>
														</DiscreteObjectKeyFrame>
													</ObjectAnimationUsingKeyFrames>
													<ObjectAnimationUsingKeyFrames Duration="0" Storyboard.TargetProperty="Foreground" Storyboard.TargetName="ContentControl">
														<DiscreteObjectKeyFrame KeyTime="0" Value="{StaticResource LightForegroundBrush}" />
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Unchecked" />
											<VisualState x:Name="Indeterminate" />
										</VisualStateGroup>
										<VisualStateGroup x:Name="FocusStates">
											<VisualState x:Name="Focused">
												<Storyboard>
													<ObjectAnimationUsingKeyFrames Storyboard.TargetProperty="(UIElement.Visibility)" Storyboard.TargetName="FocusedVisualElement">
														<DiscreteObjectKeyFrame KeyTime="0">
															<DiscreteObjectKeyFrame.Value>
																<Visibility>Visible</Visibility>
															</DiscreteObjectKeyFrame.Value>
														</DiscreteObjectKeyFrame>
													</ObjectAnimationUsingKeyFrames>
												</Storyboard>
											</VisualState>
											<VisualState x:Name="Unfocused" />
										</VisualStateGroup>
									</VisualStateManager.VisualStateGroups>
									<Rectangle x:Name="Bd" Fill="{StaticResource ButtonBackgroundBrush}" Stroke="{StaticResource ButtonBorderBrush}" StrokeThickness="1" />
									<Rectangle x:Name="checked" Fill="{StaticResource ButtonPressedBackgroundBrush}" Stroke="{StaticResource ButtonPressedBorderBrush}" StrokeThickness="1" Visibility="Collapsed" />
									<ContentControl x:Name="ContentControl" Foreground="{TemplateBinding Foreground}" HorizontalAlignment="{TemplateBinding HorizontalContentAlignment}" Margin="{TemplateBinding Padding}" VerticalAlignment="{TemplateBinding VerticalContentAlignment}">
										<ContentPresenter x:Name="contentPresenter" />
									</ContentControl>
									<Rectangle x:Name="FocusedVisualElement" Stroke="{StaticResource ButtonPressedBorderBrush}" Visibility="Collapsed" StrokeThickness="2" />
									<Rectangle x:Name="DisabledVisualElement" Fill="{StaticResource DisabledVisualElement}" Visibility="Collapsed" />
								</Grid>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<BorderGapMaskConverter x:Key="BorderGapMaskConverter" />
				<Style x:Key="GroupBoxStyle" TargetType="{x:Type GroupBox}">
					<Setter Property="FontFamily" Value="Segoe UI" />
					<Setter Property="FontSize" Value="14.667" />
					<Setter Property="Foreground" Value="{StaticResource ForegroundBrush}" />
					<Setter Property="BorderBrush" Value="{StaticResource GroupBoxBorderBrush}" />
					<Setter Property="BorderThickness" Value="1" />
					<Setter Property="Padding" Value="5" />
					<Setter Property="SnapsToDevicePixels" Value="True" />
					<Setter Property="Template">
						<Setter.Value>
							<ControlTemplate TargetType="{x:Type GroupBox}">
								<Grid SnapsToDevicePixels="true">
									<Grid.ColumnDefinitions>
										<ColumnDefinition Width="6" />
										<ColumnDefinition Width="Auto" />
										<ColumnDefinition Width="*" />
										<ColumnDefinition Width="6" />
									</Grid.ColumnDefinitions>
									<Grid.RowDefinitions>
										<RowDefinition Height="Auto" />
										<RowDefinition Height="Auto" />
										<RowDefinition Height="*" />
										<RowDefinition Height="6" />
									</Grid.RowDefinitions>
									<Border BorderBrush="{StaticResource TransparentBrush}" BorderThickness="{TemplateBinding BorderThickness}" Background="{TemplateBinding Background}" Grid.ColumnSpan="4" Grid.Column="0" Grid.Row="1" Grid.RowSpan="3" />
									<Border x:Name="Header" Grid.Column="1" Padding="10,0,10,0" Grid.Row="0" Grid.RowSpan="2">
										<ContentPresenter ContentSource="Header" Height="20" RecognizesAccessKey="True" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" />
									</Border>
									<ContentPresenter Grid.ColumnSpan="2" Grid.Column="1" Margin="{TemplateBinding Padding}" Grid.Row="2" SnapsToDevicePixels="{TemplateBinding SnapsToDevicePixels}" />
									<Border Grid.ColumnSpan="4" Grid.Row="1" Grid.RowSpan="3">
										<Border.OpacityMask>
											<MultiBinding ConverterParameter="7" Converter="{StaticResource BorderGapMaskConverter}">
												<Binding ElementName="Header" Path="ActualWidth" />
												<Binding Path="ActualWidth" RelativeSource="{RelativeSource Self}" />
												<Binding Path="ActualHeight" RelativeSource="{RelativeSource Self}" />
											</MultiBinding>
										</Border.OpacityMask>
										<Border BorderBrush="{TemplateBinding BorderBrush}" BorderThickness="{TemplateBinding BorderThickness}"/>
									</Border>
								</Grid>
							</ControlTemplate>
						</Setter.Value>
					</Setter>
				</Style>
				<Style BasedOn="{StaticResource ButtonStyle}" TargetType="{x:Type Button}" />
				<Style BasedOn="{StaticResource ScrollBarStyle}" TargetType="{x:Type ScrollBar}" />
				<Style BasedOn="{StaticResource ScrollViewerStyle}" TargetType="{x:Type ScrollViewer}" />
				<Style BasedOn="{StaticResource ComboBoxStyle}" TargetType="{x:Type ComboBox}" />
				<Style BasedOn="{StaticResource ComboBoxItemStyle}" TargetType="{x:Type ComboBoxItem}" />
				<Style BasedOn="{StaticResource TextBoxStyle}" TargetType="{x:Type TextBox}" />
				<Style BasedOn="{StaticResource ListBoxStyle}" TargetType="{x:Type ListBox}" />
				<Style BasedOn="{StaticResource ListBoxItemStyle}" TargetType="{x:Type ListBoxItem}" />
				<Style BasedOn="{StaticResource CheckBoxStyle}" TargetType="CheckBox">
					<Setter Property="VerticalContentAlignment" Value="Top" />
				</Style>
				<Style BasedOn="{StaticResource RadioButtonStyle}" TargetType="{x:Type RadioButton}" />
				<Style BasedOn="{StaticResource LabelStyle}" TargetType="{x:Type Label}" />
				<Style BasedOn="{StaticResource SliderStyle}" TargetType="{x:Type Slider}" />
				<Style BasedOn="{StaticResource RepeatButtonStyle}" TargetType="{x:Type RepeatButton}" />
				<Style BasedOn="{StaticResource GridSplitterStyle}" TargetType="{x:Type GridSplitter}" />
				<Style BasedOn="{StaticResource ProgressBarStyle}" TargetType="{x:Type ProgressBar}" />
				<Style BasedOn="{StaticResource PasswordBoxStyle}" TargetType="{x:Type PasswordBox}" />
				<Style BasedOn="{StaticResource ExpanderStyle}" TargetType="{x:Type Expander}" />
				<Style BasedOn="{StaticResource ToggleButtonStyle}" TargetType="{x:Type ToggleButton}" />
				<Style BasedOn="{StaticResource GroupBoxStyle}" TargetType="{x:Type GroupBox}" />
			</ResourceDictionary>
		</ResourceDictionary.MergedDictionaries>
	</ResourceDictionary>
</Window.Resources>

<Grid>
 <Border BorderBrush="Black" BorderThickness="1" HorizontalAlignment="Left" Height="128" VerticalAlignment="Top" Width="1076" Margin="1,1,0,0" Background="#1a84d1">
</Border>
</Grid></Window>
"@

#-------------------------------------------------------------#
#----Control Event Handlers-----------------------------------#
#-------------------------------------------------------------#


#region Logic
#Write your code here
#endregion 


#-------------------------------------------------------------#
#----Script Execution-----------------------------------------#
#-------------------------------------------------------------#

$Window = [Windows.Markup.XamlReader]::Parse($Xaml)

[xml]$xml = $Xaml

$xml.SelectNodes("//*[@Name]") | ForEach-Object { Set-Variable -Name $_.Name -Value $Window.FindName($_.Name) }







$Global:SyncHash = [HashTable]::Synchronized(@{})
$SyncHash.Window = $Window
$Jobs = [System.Collections.ArrayList]::Synchronized([System.Collections.ArrayList]::new())
$initialSessionState = [initialsessionstate]::CreateDefault()

Function Start-RunspaceTask
{
    [CmdletBinding()]
    Param([Parameter(Mandatory=$True,Position=0)][ScriptBlock]$ScriptBlock,
          [Parameter(Mandatory=$True,Position=1)][PSObject[]]$ProxyVars)
            
    $Runspace = [RunspaceFactory]::CreateRunspace($InitialSessionState)
    $Runspace.ApartmentState = 'STA'
    $Runspace.ThreadOptions  = 'ReuseThread'
    $Runspace.Open()
    ForEach($Var in $ProxyVars){$Runspace.SessionStateProxy.SetVariable($Var.Name, $Var.Variable)}
    $Thread = [PowerShell]::Create('NewRunspace')
    $Thread.AddScript($ScriptBlock) | Out-Null
    $Thread.Runspace = $Runspace
    [Void]$Jobs.Add([PSObject]@{ PowerShell = $Thread ; Runspace = $Thread.BeginInvoke() })
}

$JobCleanupScript = {
    Do
    {    
        ForEach($Job in $Jobs)
        {            
            If($Job.Runspace.IsCompleted)
            {
                [Void]$Job.Powershell.EndInvoke($Job.Runspace)
                $Job.PowerShell.Runspace.Close()
                $Job.PowerShell.Runspace.Dispose()
                $Job.Powershell.Dispose()
                
                $Jobs.Remove($Job)
            }
        }

        Start-Sleep -Seconds 1
    }
    While ($SyncHash.CleanupJobs)
}

Get-ChildItem Function: | Where-Object {$_.name -notlike "*:*"} |  select name -ExpandProperty name |
ForEach-Object {       
    $Definition = Get-Content "function:$_" -ErrorAction Stop
    $SessionStateFunction = New-Object System.Management.Automation.Runspaces.SessionStateFunctionEntry -ArgumentList "$_", $Definition
    $InitialSessionState.Commands.Add($SessionStateFunction)
}


$Window.Add_Closed({
    Write-Verbose 'Halt runspace cleanup job processing'
    $SyncHash.CleanupJobs = $False
})

$SyncHash.CleanupJobs = $True
function Async($scriptBlock){ Start-RunspaceTask $scriptBlock @([PSObject]@{ Name='DataContext' ; Variable=$DataContext},[PSObject]@{Name="State"; Variable=$State},[PSObject]@{Name = "SyncHash";Variable = $SyncHash})}

Start-RunspaceTask $JobCleanupScript @([PSObject]@{ Name='Jobs' ; Variable=$Jobs })



$Window.ShowDialog()


