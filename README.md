# Motion for Flutter widgets

This package adds a new `Motion` widget that applies a gyroscope-based effect to Flutter widgets.


!["Demo of the Motion plugin"](example/gifs/demo.gif)

To see examples of the following effect on a device or simulator:

```bash
cd example/
flutter run --release
```

## How to use 

Wrap your target widget as child of a [Motion] widget. You are required to provide a [MotionController] instance that will hold your widget's transformations. The simplest usage of this widget is the following :

```dart

import 'package:motion/motion.dart';

final controller = MotionController();

...

return Motion(
    elevation: 7,
    controller: controller,
    child: myWidget,
);

```

### Elevation

To remain consistent with the Material design language, you can pass an **elevation** parameter to the widget. 

It will influence the offset, opacity and blurriness of the shadow. Possible values range between `0` and `100`.

!["Elevations examples"](example/gifs/elevations.gif)

_Comparing different elevations_

### Shadow

The **shadow** is optional and depends, if enabled, on the `elevation` value. This higher the `elevation`, the blurrier and the lower the shadow will get from behind the widget, just like in the Material design language. The amplitude of its movement is also controlled by the `elevation`.

!["Shadow effect comparison"](example/gifs/shadow.gif)

_Comparing with and without the shadow effect_

By default, the `shadow` is enabled but you can disable it by constructing the `Motion` widget, with `shadow: false`.

### Glare

The **glare** effect is also optional. It is a very subtle gradient overlay that confers a reflective feel to the widget.

!["Glare effect comparison"](example/gifs/glare.gif)

_Comparing with and without the glare effect_

Also enabled by default, you can disable this effect by constructing the `Motion` widget, with `glare: false`.

