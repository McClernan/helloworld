Material Dialogs
In HTML there are three dialog types: alert, confirm and prompt.
Google Material
A dialog is a type of modal window that appears in front of app content to provide critical information, or ask for a decision. Dialogs disable all app functionality when they appear, and remain on screen until confirmed, dismissed, or a required action has been taken.
Material.io
Dialogs inform users about a task and can contain critical information, require decisions, or involve multiple tasks.

Dialogs share some functionality with sheets in Android:
as we consider the broader family of sheet components, we have an opportunity to support a wider range of scenarios (and address current limitations of modal dialogs) through the introduction of floating sheets.  

Short term, for V1, our guidance will cover visual and interaction updates for Dialogs, Bottom sheets and Side sheets, empowering app builders to design for both large screens as well as foldable devices. 
 
Long term, post V1, we plan to introduce floating sheets as a new component, to support a wider range of communication and action flows beyond our modal and simple dialog variants. 

Dialogs are interchangeable with bottom sheets

Proposal for Taxonomy (near term, V1)
Component > Container > Dialogs
No change. Dialogs remain modal and blocking, carrying over the same guidance and options as they exist today in GM spec. 
Component > Container > Bottom Sheets
Depending on screen size, Bottom sheets can change into Side Sheets and vice-versa, but they do not change into Dialogs or Menus.
Component > Container > Side Sheets
No change from baseline. 

Proposal for Taxonomy (Post-V1) 
Component > Container > Dialog
Dialogs remain modal and disruptive. (what is the difference between modal and disruptive in this context?)
Component > Container > Sheet > Docked
Docked sheets can either be bottom or side docked, and can transition from one to the other depending on screen size. 
Component > Container > Sheet > Floating
Floating sheets are assistive and non-modal.

Dialog Issue: simplify, consolidate
Simplify dialogs into “Basic dialog” and “Full-screen dialog”
List out “alert” and “simple” and “confirmation” as common configurations or common examples of dialogs
Ask eng folk for a list of their dialog implementations
Here’s what we propose – basic and full-screen
Alex to poke around for Figma of dialogs — everyone drop your notes in here so we know we can represent it accurately per platform
 
https://docs.google.com/document/d/1zk5vbX2CJgjz6UXxxGlMV2xVrxD4nZRsjBe06FofNhQ/edit?resourcekey=0-WaEl8O8y17Hp9uiJ-gqdeg
Material Next - Adaptive Sheets and Dialogs: One-Pager
Android
Github
https://github.com/material-components/material-components-android/blob/master/docs/components/Dialog.md
Alert dialog
Simple dialog
Confirmation dialog
Full-screen dialog
Material IO 
https://material.io/components/dialogs
Alert dialog
Simple dialog
Confirmation dialog
Full-screen dialog
Flutter
https://github.com/material-components/material-components-flutter/blob/develop/docs/components/dialogs.md
https://material.io/components/dialogs#usage
Alert dialog
Simple dialog
Confirmation dialog
Full-screen dialog

Dialog packages unrelated to Material
https://pub.dev/flutter/packages?q=dialog
Flutter API libraries
Material is one of the libraries and “how flutter widgets implement Material Design”
MH - simplify types
Basic dialog and full screen
Dialog devdoc for flutter

Goal: dialog buckets, Flutter wireframe

Flutter widgets implementing Material Design
AboutDialog class 
An about box. This is a dialog box with the application's icon, name, version number, and copyright, plus a button to show licenses for software used by the application.
AlertDialog class
A material design alert dialog.
An alert dialog informs the user about situations that require acknowledgement. An alert dialog has an optional title and an optional list of actions. The title is displayed above the content and the actions are displayed below the content.
DatePickerDialog class
A Material-style date picker dialog.
It is used internally by showDatePicker or can be directly pushed onto the Navigator stack to enable state restoration. See showDatePicker for a state restoration app example.
DateRangePickerDialog class
A Material-style date range picker dialog.
It is used internally by showDateRangePicker or can be directly pushed onto the Navigator stack to enable state restoration. See showDateRangePicker for a state restoration app example.
Dialog class
A material design dialog.
This dialog widget does not have any opinion about the contents of the dialog. Rather than using this widget directly, consider using AlertDialog or SimpleDialog, which implement specific kinds of material design dialogs.
See also:
AlertDialog, for dialogs that have a message and some buttons.
SimpleDialog, for dialogs that offer a variety of options.
showDialog, which actually displays the dialog and returns its result.
material.io/design/components/dialogs.html
DialogRoute<T> class
A dialog route with Material entrance and exit animations, modal barrier color, and modal barrier behavior (dialog is dismissible with a tap on the barrier).
It is used internally by showDialog or can be directly pushed onto the Navigator stack to enable state restoration. See showDialog for a state restoration app example.
DialogTheme class
Defines a theme for Dialog widgets.
Descendant widgets obtain the current DialogTheme object using DialogTheme.of(context). Instances of DialogTheme can be customized with DialogTheme.copyWith.
Simple dialog class
A simple material design dialog.
A simple dialog offers the user a choice between several options. A simple dialog has an optional title that is displayed above the choices.
Choices are normally represented using SimpleDialogOption widgets. If other widgets are used, see contentPadding for notes regarding the conventions for obtaining the spacing expected by Material Design.
Simple Dialog Option
An option used in a SimpleDialog.
A simple dialog offers the user a choice between several options. This widget is commonly used to represent each of the options. If the user selects this option, the widget will call the onPressed callback, which typically uses Navigator.pop to close the dialog.
The padding on a SimpleDialogOption is configured to combine with the default SimpleDialog.contentPadding so that each option ends up 8 pixels from the other vertically, with 20 pixels of spacing between the dialog's title and the first option, and 24 pixels of spacing between the last option and the bottom of the dialog.
showAboutDialog(
Displays an AboutDialog, which describes the application and provides a button to show licenses for software used by the application.
The arguments correspond to the properties on AboutDialog.
If the application has a Drawer, consider using AboutListTile instead of calling this directly.
If you do not need an about box in your application, you should at least provide an affordance to call showLicensePage.
showDialog<T>({required BuildContext context, required WidgetBuilder builder, bool barrierDismissible = true, Color? barrierColor = Colors.black54, String? barrierLabel, bool useSafeArea = true, bool useRootNavigator = true, RouteSettings? routeSettings}) → Future<T?>
Displays a Material dialog above the current contents of the app, with Material entrance and exit animations, modal barrier color, and modal barrier behavior (dialog is dismissible with a tap on the barrier). [...]
showGeneralDialog<T extends Object?>({required BuildContext context, required RoutePageBuilder pageBuilder, bool barrierDismissible = false, String? barrierLabel, Color barrierColor = const Color(2147483648), Duration transitionDuration = const Duration(milliseconds: 200), RouteTransitionsBuilder? transitionBuilder, bool useRootNavigator = true, RouteSettings? routeSettings}) → Future<T?>
Displays a dialog above the current contents of the app. [...]
showTimePicker function
Future<TimeOfDay?> showTimePicker(
{required BuildContext context,
required TimeOfDay initialTime,
TransitionBuilder? builder,
bool useRootNavigator = true,
TimePickerEntryMode initialEntryMode = TimePickerEntryMode.dial,
String? cancelText,
String? confirmText,
String? helpText,
RouteSettings? routeSettings}
)
Shows a dialog containing a material design time picker.
The returned Future resolves to the time selected by the user when the user closes the dialog. If the user cancels the dialog, null is returned.
showDatePicker({required BuildContext context, required DateTime initialDate, required DateTime firstDate, required DateTime lastDate, DateTime? currentDate, DatePickerEntryMode initialEntryMode = DatePickerEntryMode.calendar, SelectableDayPredicate? selectableDayPredicate, String? helpText, String? cancelText, String? confirmText, Locale? locale, bool useRootNavigator = true, RouteSettings? routeSettings, TextDirection? textDirection, TransitionBuilder? builder, DatePickerMode initialDatePickerMode = DatePickerMode.day, String? errorFormatText, String? errorInvalidText, String? fieldHintText, String? fieldLabelText}) → Future<DateTime?>
Shows a dialog containing a Material Design date picker. [...]
showDateRangePicker({required BuildContext context, DateTimeRange? initialDateRange, required DateTime firstDate, required DateTime lastDate, DateTime? currentDate, DatePickerEntryMode initialEntryMode = DatePickerEntryMode.calendar, String? helpText, String? cancelText, String? confirmText, String? saveText, String? errorFormatText, String? errorInvalidText, String? errorInvalidRangeText, String? fieldStartHintText, String? fieldEndHintText, String? fieldStartLabelText, String? fieldEndLabelText, Locale? locale, bool useRootNavigator = true, RouteSettings? routeSettings, TextDirection? textDirection, TransitionBuilder? builder}) → Future<DateTimeRange?>
Shows a full screen modal dialog containing a Material Design date range picker. [...]
https://api.flutter.dev/flutter/material/showTimePicker.html



Accessing dialog in Flutter


Flutter Set-up
Installing Flutter on MacOS Big Sur
Requirements:
Flutter SDK
Android Studio (can use preferred editor)
Dart SDK (bundled with Flutter)
CocoaPods
Java
Terminal zsh
Kotlin
Codelab
SET UP COMPLETE
TERMINAL PATH
Export PATH=”$PATH:/Users/nancymcclernan/Desktop/flutterSDK/flutter/bin”

“IN Flutter, almost everything is a widget, including alignment, padding and layout”.
“The widget’s main job is to provide a build() method that describes how to display the widget in terms of other, lower level widgets


Start Flutter & My App
Ingredients: Simulator for iOS, Xcode Build, Dart DevTools, Android Studio
Open Android Studio then select simulator on top-left menu bar or use terminal
In terminal: open -a Simulator
It will open image (of iphone) on screen
If Simulator is not open it will open in web page localhost:61449/#/
Flutter run
MUST ADD PATH 
Export PATH=”$PATH:/Users/nancymcclernan/Desktop/flutterSDK/flutter/bin”


Change directory if this gives a “no file found” message
Changed to Desktop/namer
Flutter run
Launches xcode (mac thing)
Activating Dart DevTools
Opens hello_world.dart
In the iphone simulator it says “Whoah dude, you have pushed the button this many times”
Open Android Studio open namer project to see hello_world.dart code
The text of the app can be changed
So can the color of the primarySwatch
Hot reload is r in the terminal window (while namer is running)
If it doesn’t recognize the color (“LightBlueAccent” instead of “LightBlue” it will throw an error
Lightning bolt is the hot reload - I think you have to run the first time after that hot reload is available.
Fun fact: this is a Material app

Building Application for Device
Must have valid device/version
I used my version 6 iPad
Could not finally figure this out after several hours. Will return later.
App from scratch

Open the IDE and select Create New Flutter Project.
IDE = Android Studio
Select Flutter Application as the project type. 
Select File -> New -> New Flutter Project
In New Project window select Flutter App.
Verify the Flutter SDK path specifies the SDK’s location 
(select Install SDK… if the text field is blank) this does not exist in Android Studio
Can’t find SDK - it’s in FLUTTER DIRECTORY
Enter a project name (for example, myapp). Then click Next.
Click Finish.
Wait for Android Studio to install the SDK and create the project.
 
OpenWeather API
https://home.openweathermap.org/api_keys
Flutter install dialog(s)

