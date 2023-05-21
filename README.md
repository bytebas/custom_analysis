# 🔎 Custom Analysis

This package provides lint rules for Dart and Flutter which I usually use.

👉 Inspired and forked from the [Very Good Ventures Analysis][vgv_linter].

## Usage

To use the lints, add as a dev dependency in your `pubspec.yaml`:

```yaml
custom_analysis:
 git:
    url: https://github.com/bytebas/custom_analysis.git
    ref: main
```

You can also target to a specific release tag:

```yaml
custom_analysis:
 git:
    url: https://github.com/bytebas/custom_analysis.git
    ref: 0.1.0+2
```

Then, add an include in `analysis_options.yaml`:

```yaml
include: package:custom_analysis/analysis_options.yaml
```

## Suppressing Lints

There may be cases where specific lint rules are undesirable. Lint rules can be suppressed at the line, file, or project level.

### Line Level

To suppress a specific lint rule for a specific line of code, use an `ignore` comment directly above the line:

```dart
// ignore: public_member_api_docs
class A {}
```

### File Level

To suppress a specific lint rule of a specific file, use an `ignore_for_file` comment at the top of the file:

```dart
// ignore_for_file: public_member_api_docs

class A {}

class B {}
```

### Project Level

To suppress a specific lint rule for an entire project, modify `analysis_options.yaml`:

```yaml
include: package:custom_analysis/analysis_options.yaml
linter:
  rules:
    public_member_api_docs: true
```

[vgv_linter]: https://github.com/VeryGoodOpenSource/very_good_analysis