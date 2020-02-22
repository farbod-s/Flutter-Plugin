# Flutter-Plugin

follow steps in [developing packages & plugins](https://flutter.dev/docs/development/packages-and-plugins/developing-packages) from flutter documentations:

## Install
```bash
$ git clone https://github.com/flutter/flutter.git -b stable
$ export PATH="$PATH:`pwd`/flutter/bin"
```

## Create the package
```bash
$ flutter create -i objc -a java --org com.example --template=plugin hello
```

## Configuration
write below codes in `pubspec.yaml`:
```yaml
flutter:
  plugin:
    platforms:
      android:
        package: com.example.hello
        pluginClass: HelloPlugin
      ios:
        pluginClass: HelloPlugin

environment:
  sdk: ">=2.1.0 <3.0.0"
  # Flutter versions prior to 1.10 did not support the flutter.plugin.platforms map.
  flutter: ">=1.10.0 <2.0.0"
```

## Publish
to publish in [pub.dev](https://pub.dev/), for more info visit [publishing packages](https://dart.dev/tools/pub/publishing) from flutter documentations.

test publish:
```bash
$ flutter pub publish --dry-run
```

actual publish:
```bash
$ flutter pub publish
```

## Platform-specific codes
follow this document about [writing custom platform-specific code](https://flutter.dev/docs/development/platform-integration/platform-channels).

## Samples
there is a [github repository](https://github.com/flutter/plugins/tree/master/packages) for best practice flutter packages.
