# matrix_gesture_detector

A gesture detector which detects translation, scale and rotation gestures
and combines them into `Matrix4` object that can be used by `Transform` widget
or by low level `CustomPainter` code. You can customize types of reported
gestures by passing [shouldTranslate], [shouldScale] and [shouldRotate]
parameters.

## Getting Started

The usage is as follows:

```dart
  MatrixGestureDetector(
    onMatrixUpdate: (Matrix4 m) {
      setState(() {
        matrix = m;
      });
    },
    child: SomeWidgetThatUsesMatrix(
      matrix: matrix,
      ...
    )
  )
```
here: `SomeWidgetThatUsesMatrix` could be a `Transform` widget
([transform_demo.dart](/example/lib/transform_demo.dart)) or a `CustomPaint` widget which
`CustomPainter` uses `Matrix4` in its low level drawing code
([custom_painter_demo.dart](/example/lib/custom_painter_demo.dart)).
