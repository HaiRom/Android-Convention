# 1. Class File

# 2. Resource File
Resources file names are written in __lowercase_underscore__.
## 2.1 Drawable File
Naming conventions for drawables:


| Asset Type   | Prefix            |		Example               |
|--------------| ------------------|-----------------------------|
| Action bar   | `ab_`             | `ab_stacked.9.png`          |
| Button       | `btn_`	            | `btn_send_pressed.9.png`    |
| Dialog       | `dialog_`         | `dialog_top.9.png`          |
| Divider      | `divider_`        | `divider_horizontal.9.png`  |
| Icon         | `ic_`	            | `ic_star.png`               |
| Menu         | `menu_	`           | `menu_submenu_bg.9.png`     |
| Notification | `notification_`	| `notification_bg.9.png`     |
| Tabs         | `tab_`            | `tab_pressed.9.png`         |

Naming conventions for icons (taken from [Android iconography guidelines](http://developer.android.com/design/style/iconography.html)):

| Asset Type                      | Prefix             | Example                      |
| --------------------------------| ----------------   | ---------------------------- |
| Icons                           | `ic_`              | `ic_star.png`                |
| Launcher icons                  | `ic_launcher`      | `ic_launcher_calendar.png`   |
| Menu icons and Action Bar icons | `ic_menu`          | `ic_menu_archive.png`        |
| Status bar icons                | `ic_stat_notify`   | `ic_stat_notify_msg.png`     |
| Tab icons                       | `ic_tab`           | `ic_tab_recent.png`          |
| Dialog icons                    | `ic_dialog`        | `ic_dialog_info.png`         |

Naming conventions for selector states:

| State	       | Suffix          | Example                     |
|--------------|-----------------|-----------------------------|
| Normal       | `_normal`       | `btn_order_normal.9.png`    |
| Pressed      | `_pressed`      | `btn_order_pressed.9.png`   |
| Focused      | `_focused`      | `btn_order_focused.9.png`   |
| Disabled     | `_disabled`     | `btn_order_disabled.9.png`  |
| Selected     | `_selected`     | `btn_order_selected.9.png`  |

## 2.2 Layout File 
 WHAT_WHERE.XML
| Prefix          |  Usage             |
| ---------------- | ---------------------- | 
| activity         | contentview for activity  | 
| fragment         |view for a fragment   | 
| view           | inflated by a custom view | 
| item         |  layout used in list/recycler/gridview | 
|  layout    | layout reused using the include tag |
|  dialog    | view for dialog  |

Example
```java
activity_main: content view of the MainActivity
fragment_articledetail: view for the ArticleDetailFragment
view_menu: layout inflated by custom view class MenuView
item_article: list item in ArticleRecyclerView
layout_actionbar_backbutton: layout for an actionbar with a backbutton (too simple to be a customview)
```
	

## 2.3 Menu File
Similar to layout files, menu files should match the name of the component. For example, if we are defining a menu file that is going to be used in the `UserActivity`, then the name of the file should be `activity_user.xml`

A good practice is to not include the word `menu` as part of the name because these files are already located in the `menu` directory.

## 2.4 Values File
Resource files in the values folder should be __plural__, e.g. `strings.xml`, `styles.xml`, `colors.xml`, `dimens.xml`, `attrs.xml`

## 2.5 Raw,Xml,Anim,Animator File

# 3. Java Code Style

## 3.1 Fields definition and naming

Fields should be defined at the __top of the file__ and they should follow the naming rules listed below.

* Private, non-static field names start with __m__.
* Private, static field names start with __s__.
* Other fields start with a lower case letter.
* Static final fields (constants) are ALL_CAPS_WITH_UNDERSCORES.

Example:

```java
public class MyClass {
    public static final int SOME_CONSTANT = 42;
    public int publicField;
    private static MyClass sSingleton;
    int mPackagePrivate;
    private int mPrivate;
    protected int mProtected;
}
```

## 3.2 Logcat 
 private final String TAG = "CompletedDeliveryAtv";
 Logger.d("TAG:" + TAG, message);

## 3.3 String constants, naming, and values 

When using one of these components, you __must__ define the keys as a `static final` fields and they should be prefixed as indicated below.

| Element            | Field Name Prefix |
| -----------------  | ----------------- |
| SharedPreferences  | `PREF_`             |
| Bundle             | `BUNDLE_`           |
| Fragment Arguments | `ARGUMENT_`         |
| Intent Extra       | `EXTRA_`            |
| Intent Action      | `ACTION_`           |


# 4. Xml Code Style
## 4.1 Use self closing tags

When an XML element doesn't have any contents, you __must__ use self closing tags.

This is good:

```xml
<TextView
	android:id="@+id/text_view_profile"
	android:layout_width="wrap_content"
	android:layout_height="wrap_content" />
```

This is __bad__ :

```xml
<!-- Don\'t do this! -->
<TextView
    android:id="@+id/text_view_profile"
    android:layout_width="wrap_content"
    android:layout_height="wrap_content" >
</TextView>
```

## 4.2 Resources naming

Resource IDs and names are written in __lowercase_underscore__.

### 4.2.1 ID naming
IDs should be prefixed with the name of the element in lowercase underscore. For example:

| Element            | Prefix            |
| -----------------  | ----------------- |
| `TextView`           | `tv_`             |
| `ImageView`          | `img_`            |
| `Button`             | `btn_`           |
| `Menu`               | `menu_`             |
| `LinearLayout`               | `ll_`             |
| `RelativeLayout`               | `rl_`             |
| `FrameLayout`               | `fr_`             |
| `EditText`               | `edt_`             |

reused using the include tag
