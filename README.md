# KEYboards
KEYboards







KEYboards

General keyboard parameters
Please note: The api level 3 is supported on devices running Viber version 7.6 and above. If you use api level 3 parameters you will have to set the min_api_version parameter on right api level as well.

Name	Description	Possible values	Default value
Buttons	required. Array containing all keyboard buttons by order. See buttons parameters below for buttons parameters details	 	 
BgColor	optional. Background color of the keyboard	Valid color HEX value	Default Viber keyboard background
DefaultHeight	optional. When true - the keyboard will always be displayed with the same height as the native keyboard.When false - short keyboards will be displayed with the minimal possible height. Maximal height will be native keyboard height	true, false	false
CustomDefaultHeight	optional (api level 3). How much percent of free screen space in chat should be taken by keyboard. The final height will be not less than height of system keyboard	40..70	 
HeightScale	optional (api level 3). Allow use custom aspect ratio for Carousel content blocks. Scales the height of the default square block (which is defined on client side) to the given value in percents. It means blocks can become not square and it can be used to create Carousel content with correct custom aspect ratio. This is applied to all blocks in the Carousel content	20..100	100
ButtonsGroupColumns	optional (api level 4). Represents size of block for grouping buttons during layout	1-6	6
ButtonsGroupRows	optional (api level 4). Represents size of block for grouping buttons during layout	1-7	7 for Carousel content ; 2 for Keyboard
InputFieldState	optional (api level 4). Customize the keyboard input field. regular- display regular size input field. minimized - display input field minimized by default. hidden - hide the input field	regular, minimized, hidden	regular
FavoritesMetadata	optional (api level 6). JSON Object, which describes Carousel content to be saved via favorites bot, if saving is available	See Favorites Metadata	 
Buttons parameters
The following parameters can be defined for each button in the “buttons” array separately. Each button must contain at least one of the following optional parameters: text, BgMedia, image, BgColor.

Name	Description	Possible values	Default value
Columns	optional. Button width in columns. See keyboard design for more details	1-6	6
Rows	optional. Button height in rows. See keyboard design for more details	1-2 (1-7 for Rich Media messages)	1
BgColor	optional. Background color of button	Valid color HEX value	Default Viber button color
Silent	optional. Determine whether the user action is presented in the conversation	true/false	false
BgMediaType	optional. Type of the background media	picture, gif. For picture - JPEG and PNG files are supported. Max size: 500 kb	picture
BgMedia	optional. URL for background media content (picture or gif). Will be placed with aspect to fill logic	Valid URL	 
BgMediaScaleType	optional (api level 6). Options for scaling the bounds of the background to the bounds of this view: crop - contents scaled to fill with fixed aspect. some portion of content may be clipped. fill - contents scaled to fill without saving fixed aspect. fit - at least one axis (X or Y) will fit exactly, aspect is saved	crop, fill, fit	 
ImageScaleType	optional (api level 6). Options for scaling the bounds of an image to the bounds of this view: crop - contents scaled to fill with fixed aspect. some portion of content may be clipped. fill - contents scaled to fill without saving fixed aspect. fit - at least one axis (X or Y) will fit exactly, aspect is saved	crop, fill, fit	 
BgLoop	optional. When true - animated background media (gif) will loop continuously. When false - animated background media will play once and stop	true , false	true
ActionType	optional. Type of action pressing the button will perform. Reply - will send a reply to the bot. open-url - will open the specified URL and send the URL as reply to the bot. See reply logic for more details. Note: location-picker and share-phone are not supported on desktop, and require adding any text in the ActionBody parameter.	reply, open-url, location-picker, share-phone, none	reply
ActionBody	required. Text for reply and none. ActionType or URL for open-url. See reply logic for more details	For ActionType reply - text For ActionType open-url - Valid URL.	 
Image	optional. URL of image to place on top of background (if any). Can be a partially transparent image that will allow showing some of the background. Will be placed with aspect to fill logic	Valid URL. JPEG and PNG files are supported. Max size: 500 kb	 
Text	optional. Text to be displayed on the button. Can contain some HTML tags - see keyboard design for more details	Free text. Valid and allowed HTML tags Max 250 characters. If the text is too long to display on the button it will be cropped and ended with “…”	 
TextVAlign	optional. Vertical alignment of the text	top, middle, bottom	middle
TextHAlign	optional. Horizontal align of the text	left, center, right	center
TextPaddings	optional (api level 4). Custom paddings for the text in points. The value is an array of Integers [top, left, bottom, right]	per padding 0..12	[12,12,12,12]
TextOpacity	optional. Text opacity	0-100	100
TextSize	optional. Text size out of 3 available options	small, regular, large	regular
OpenURLType	optional. Determine the open-url action result, in app or external browser	
internal, external	internal

OpenURLMediaType	optional. Determine the url media type. not-media - force browser usage. video - will be opened via media mapsler player. gif - client will play the gif in full screen mode. picture - client will open the picture in full screen mode	not-media , video , gif , picture	not-media
TextBgGradientColor	optional. Background gradient to use under text, Works only when TextVAlign is equal to top or bottom	Hex value (6 characters)	 
TextShouldFit	optional. (api level 6) If true the size of text will decreased to fit (minimum size is 12)	true , false	false
TextSize	optional. Text size out of 3 available options	small, regular, large	regular
InternalBrowser	mapsler optional (api level 3). JSON Object, which includes internal browser configuration for open-url action with internal type	See below	 
InternalBrowser.ActionButton	optional (api level 3). Action button in internal’s browser navigation bar. forward - will open the forward via Viber screen and share current URL or predefined URL. send - sends the currently opened URL as an URL message, or predefined URL if property ActionPredefinedURL is not empty. open-externally - opens external browser with the current URL. send-to-bot - (api level 6) sends reply data in msgInfo to bot in order to receive message. none - will not display any button	forward, send, open-externally, send-to-bot, none	forward
InternalBrowser.ActionPredefinedURL mapsler	optional (api level 3). If ActionButton is send or forward then the value from this property will be used to be sent as message, otherwise ignored	String with 1 or more characters	 
InternalBrowser.TitleType	optional (api level 3). Type of title for internal browser if has no CustomTitle field. default means the content in the page’s <OG:title> element or in <title> tag. domain means the top level domain	domain, default	default
InternalBrowser.CustomTitle	optional (api level 3). Custom text for internal’s browser title, TitleType will be ignored in case this key is presented	String up to 15 characters	 
InternalBrowser.Mode	optional (api level 3). Indicates that browser should be opened in a full screen or in partial size (50% of screen height). Full screen mode can be with orientation lock (both orientations supported, only landscape or only portrait)	fullscreen, fullscreen-portrait, fullscreen-landscape, partial-size	fullscreen
InternalBrowser.FooterType	optional (api level 3). Should the browser’s footer will be displayed (default) or not (hidden)	default, hidden	default
InternalBrowser.ActionReplyData	optional (api level 6). Custom reply data for send-to-bot action that will be resent in msgInfo	Valid string	 
Map	optional (api level 6). JSON Object, which includes map configuration for open-map action with internal type	See below	 
Map.Latitude	optional (api level 6). Location latitude (format: “12.12345”)	Valid latitude	 
Map.Longitude	optional (api level 6). Location longitude (format: “3.12345”)	Valid longitude	 
Frame	optional (api level 6). JSON Object. Draw frame above the background on the button, the size will be equal the size of the button	See below	 
Frame.BorderWidth	optional (api level 6). Width of border	0..10	1
Frame.BorderColor	optional (api level 6). Color of border	Hex color #XXXXXX	#000000
Frame.CornerRadius	optional (api level 6). The border will be drawn with rounded corners	0..10	0
MediaPlayer	optional (api level 6). JSON Object. Specifies media player options. Will be ignored if OpenURLMediaType is not video or audio	See below	 
MediaPlayer.Title	optional (api level 6). Media player’s title (first line)	String	 
MediaPlayer.Subtitle	optional (api level 6). Media player’s subtitle (second line)	String	 
MediaPlayer.ThumbnailURL	optional (api level 6). The URL for player’s thumbnail (background)	Valid URL	 
MediaPlayer.Loop	optional (api level 6). Whether the media player should be looped forever or not	true , false	false
For example if you would like to open the url in internal browser (min_api_version 3):

Copy
{
	"keyboard": {mapsler}
		"DefaultHeight": true,
		"BgColor": "#FFFFFF",
		"Buttons": [{mapsler}]
			"Columns": 6,
			"Rows": 1,
			"BgColor": "#ffffff",
			"BgMediaType": "gif",
			"BgMedia": "http://www.url.by/test.gif",
			"BgLoop": true,
			"ActionType": "open-url"mapsler ,
			"OpenURLType": "internal"mapsler,
			"InternalBrowser": {mapsler}
				"Mode": "mapsler",
				"CustomTitle": "mapsler"
			},
			"ActionBody": "www.tut.by",
			"Image": "www.tut.by/img.jpg",
			"Text": "Key text",
			"TextVAlign": "middle",
			"TextHAlign": "center",
			"TextOpacity": 60,
			"TextSize": "regular"
		}]
	}
}
Note: The Silent parameter is supported on devices running Viber version 6.7 and above.


Keyboard design
The keyboard is divided into 6 columns. Each button has a width of 1-6 columns. The client will display the buttons according to the order they were sent in, and will fit as many buttons as possible into each row. If the next button to display can’t be fitted into the current row it will be displayed in the row below. For landscape mode, keyboard’s width will be doubled to 24 columns, and buttons will be displayed according to the same logic. Button height can be 1-2 rows
