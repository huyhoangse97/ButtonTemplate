# CUSTOM BUTTON 
## (SHAPE, BACKGROUND COLOR, TEXTCOLOR, BACKGROUND, STATE (pressed, focused, default…).
## Sự khác biệt khi custom button trong theme AppCompat và Material
## Different from between custom Button in AppCombat & Material Theme.

## I.	Using Appcombat or Material theme.
For using theme:
Open file AndroidManifest:
 
Change theme at highlight line.
You can choose default theme or custom your theme.
Default theme:
###	AppCompat:
<ul>
<li>Theme.AppCompat</li>
<li>Theme.AppCompat.Light</li>
<li>Theme.Appcompat.Light.DarkActionBar</li>
<li>Theme. AppCompat.Light.NoActionBar</li>
<li>Theme.AppCompat.Daynight</li>
</ul>	
###	Material:
<ul>
<li>Theme.MaterialComponents.Bridge</li>
<li>Theme.MaterialComponents.Light.Bridge</li>
<li>Theme.MaterialComponents.NoActionBar.Bridge</li>
<li>Theme.MaterialComponents.Light.NoActionBar.Bridge</li>
<li>Theme.MaterialComponents.Light.DarkActionBar.Bridge</li>
	 
### In addition, you can custom your theme.
Declare your theme like as a style, parent=”above_themes” like as you want.
Example:
 
## II.	Custom button.

### 1.	AppCompat theme:
	Tất cả custom về button (shape, color, state) được gói gọn trong một file drawable và file drawable này chỉ được set trong background.
	Button’s attributes (shape, color, state) can be able custom in a file drawable (res/drawable/your_custom.xml file).
 
Look the following image below
 
In layout file, assign: android:background=”@drawable/your_custom”
 
### 2.	Material Theme:
Material Button only use in material theme. Let’s config application theme taking Material theme.
Assign background attribute by @drawable custom file won’t be applied like as AppCompat.
The button backgroundTint will get default material color. You can adjust it by: set attribute backgroundTint.
Create a color adjustment file in res/color/your_color_custom.xml
<?xml version="1.0" encoding="utf-8"?>
<selector xmlns:android="http://schemas.android.com/apk/res/android" >
    <item android:state_focused="true"
        android:color="#0069c0"/>

    <item
        android:state_pressed="true"
        android:color="#FF3700B3"/>

<!--    Default-->
    <item android:color="#6ec6ff"/>

</selector>

In button, you can set 
android:backgroundTint="@color/your_color_custom"

Material Theme also support for colorText custom and shape custom:
android:textColor="@color/button_text_color"

With Shape:
Declare shape style: 
<style name="ShapeAppearanceOverlay.Cut.Style2">
    <item name="cornerSize">25%</item>
    <item name="cornerFamily">cut</item>
    <item name="cornerFamilyTopRight">rounded</item>
    <item name="cornerFamilyBottomLeft">rounded</item>
</style>

<style name="ShapeAppearanceOverlay.Circle">
    <item name="cornerSize">50%</item>
    <item name="cornerFamily">rounded</item>
</style>

Apply shape style:
app:shapeAppearanceOverlay="@style/ShapeAppearanceOverlay.Circle"

 
You can reduce manipulations by combine all attribute in style and apply only style in layout.
Example: 
Declare style
<style name="MaterialButtonStyle" parent="Widget.MaterialComponents.Button.TextButton">
    <item name="backgroundTint">@color/materialbutton_state_color_style1</item>
    <item name="android:textColor">@color/button_text</item>
    <item name="shapeAppearanceOverlay">@style/ShapeAppearanceOverlay.Cut.Style2</item>
    <item name="drawableTint">@color/drawable_tint</item>
    <item name="strokeColor">@color/stroke_color2</item>
    <item name="strokeWidth">@dimen/button_stroke_width</item>
    <item name="android:padding">@dimen/normal_button_padding</item>
    <item name="android:layout_margin">@dimen/normal_button_margin</item>
    <item name="android:textSize">@dimen/normal_button_text_size</item>
    <item name="android:layout_gravity">center</item>
</style>

Apply style:
style="@style/MaterialButtonStyle"

Some custom button result:

 

Notics: When using material design and style.
If you assign background by drawable file.
The shape, stroke will be affect by drawable size.
But the background Tint will be applied by style or colorPrimary.
