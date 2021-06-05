Notic the theme:
	When using theme: MaterialComponents
	The color of button will be set by colorPrimary.
So, change to other theme, such as: Theme.AppCompat.Light.DarkActionBar

Change App theme if you want to apply all.
Or Create new style just for only Button


>>Color: Phân cấp (priority)
	BackgroundTint > Background > colorButtonNormal (in theme).
	If (backgroundTint and Background are set at the same time. BackgroundTint will be applied to button color instead of background
and shape in drawable (of background) is still applied.)
	If both BackgroundTint and Background color are unset, colorButtonNormal will be applied.


>>Style Button and Theme template (material button, floattingButton, etc.):


	