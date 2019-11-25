[![pub package](https://img.shields.io/pub/v/assorted_layout_widgets.svg)](https://pub.dartlang.org/packages/assorted_layout_widgets)

# assorted_layout_widgets

Widgets in this package:

* `ColumnSuper`
* `RowSuper`
* `FitHorizontally`

I will slowly but surely add interesting widgets to this package.


## ColumnSuper

Given a list of children widgets, this will arrange them in a column.
It can overlap cells, add separators and more.

```dart
ColumnSuper({  
    List<Widget> children,    
    double outerDistance,
    double innerDistance,
    bool invert,
    Alignment alignment,
    Widget separator,
    bool separatorOnTop,
  });
```

* **`children`** is the list of widgets that represent the column cells, just like in a regular `Column` widget.
The list may contain `null`s, which will be ignored.
 
* **`outerDistance`** is the distance in pixels before the first and after the last widget.
It can be negative, in which case the cells will overflow the column.
 
* **`innerDistance`** is the distance in pixels between the cells. 
It can be negative, in which case the cells will overlap.

* **`invert`** if true will paint the cells that come later on top of the ones that came before.
This is specially useful when cells overlap (negative `innerDistance`).

* **`alignment`** will align the cells horizontally if they are smaller than the available horizontal space.

* **`separator`** is a widget which will be put between each cells. Its height doesn't matter,
 since the distance between cells is given by `innerDistance`.   

* **`separatorOnTop`** if `true` (the default) will paint the separator on top of the cells.
If `false` will paint the separator below the cells.

*Note: This is not a substitute for Flutter's native Column, 
it doesn't try to have a similar API, and it doesn't do all that the native Column does.*

Try running the <a href="https://github.com/marcglasberg/assorted_layout_widgets/blob/master/example/lib/main_column_super.dart">example</a>.


## RowSuper

Same as `ColumnSuper`, but for a row.

```dart
RowSuper({  
    List<Widget> children,    
    double outerDistance,
    double innerDistance,
    bool invert,
    Alignment alignment,
    Widget separator,
    bool separatorOnTop,
  });
```                      

Try running the <a href="https://github.com/marcglasberg/assorted_layout_widgets/blob/master/example/lib/main_row_super.dart">example</a>.


## FitHorizontally

```dart
FitHorizontally({
    Widget child,  
    double shrinkLimit,
    bool fitsHeight,
    AlignmentGeometry alignment,
  });
```                      

The `child` will be asked to define its own intrinsic height.
If `fitsHeight` is true, the child will be proportionately resized (keeping its aspect ratio)
to fit the available height.

Then, if the child doesn't fit the width, it will be shrinked horizontally
only (not keeping its aspect ratio) until if fits, unless `shrinkLimit` is larger than zero, 
in which case it will shrink only until that limit. 
Note if `shrinkLimit` is 1.0 the child
will not shrink at all. The default is 0.67 (67%).

This is specially useful for text that is displayed in a single line.
When text doesn't fit the container it will shrink only horizontally,
until it reaches the shrink limit. From that point on it will clip,
display ellipsis or fade, according to the text's `Text.overflow` property.

## AlignPositioned

See package <a href="https://pub.dev/packages/align_positioned">align_positioned</a>
for widgets `AlignPositioned` and its siblings `AnimatedAlignPositioned` and `AnimChain`.
They should be part of this package, but will remain in their own package for historical reasons.

***

*The Flutter packages I've authored:* 
* <a href="https://pub.dev/packages/async_redux">async_redux</a>
* <a href="https://pub.dev/packages/provider_for_redux">provider_for_redux</a>
* <a href="https://pub.dev/packages/i18n_extension">i18n_extension</a>
* <a href="https://pub.dev/packages/align_positioned">align_positioned</a>
* <a href="https://pub.dev/packages/network_to_file_image">network_to_file_image</a>
* <a href="https://pub.dev/packages/matrix4_transform">matrix4_transform</a> 
* <a href="https://pub.dev/packages/back_button_interceptor">back_button_interceptor</a>
* <a href="https://pub.dev/packages/indexed_list_view">indexed_list_view</a> 
* <a href="https://pub.dev/packages/animated_size_and_fade">animated_size_and_fade</a>
* <a href="https://pub.dev/packages/assorted_layout_widgets">assorted_layout_widgets</a>

<br>_Marcelo Glasberg:_<br>
_https://github.com/marcglasberg_<br>
_https://twitter.com/glasbergmarcelo_<br>
_https://stackoverflow.com/users/3411681/marcg_<br>
_https://medium.com/@marcglasberg_<br>

