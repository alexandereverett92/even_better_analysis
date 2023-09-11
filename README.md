# Even Better Analysis

Analysis options that are pretty much just the ones used in the flutter repo.
Changes are for package level imports and to allow one line if statements:

```dart
if (!mounted) return;
```

[![pub package][pub_badge]][pub_badge_link]
[![License: MIT][license_badge]][license_badge_link]
[![style: even better analysis][badge]][badge_link]

---

**Note**: This package was heavily inspired by [pedantic][pedantic_link].

## Usage

To use the lints, add as a dev dependency in your `pubspec.yaml`:

```yaml
dart pub add dev:even_better_analysis
# or
flutter pub add dev:even_better_analysis
```

Then, add an include in `analysis_options.yaml`:

```yaml
include: package:even_better_analysis/analysis_options.yaml
```

This will ensure you always use the latest version of the lints. If you wish to restrict the lint version, specify a version of `analysis_options.yaml` instead:

```yaml
include: package:even_better_analysis/analysis_options.1.0.0.yaml
```

## Suppressing Lints

There may be cases where specific lint rules are undesirable. Lint rules can be suppressed at the line, file, or project level.

An example use case for suppressing lint rules at the file level is suppressing the `prefer_const_constructors` in order to achieve 100% code coverage. This is due to the fact that const constructors are executed before the tests are run, resulting in no coverage collection.

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
include: package:even_better_analysis/analysis_options.yaml
linter:
  rules:
    public_member_api_docs: false
```

## Badge

To indicate your project is using `even_better_analysis` →
[![style: even_better_analysis][badge]][badge_link]

```md
[![style: even_better_analysis](https://img.shields.io/badge/style-even_better_analysis-8602C9.svg)](https://pub.dev/packages/even_better_analysis)
```

[analysis_options_yaml]: https://github.com/alexandereverett92/even_better_analysis/blob/main/lib/analysis_options.1.0.0.yaml
[badge]: https://img.shields.io/badge/style-even_better_analysis-8602C9.svg
[badge_link]: https://pub.dev/packages/even_better_analysis
[license_badge]: https://img.shields.io/badge/license-MIT-blue.svg
[license_badge_link]: https://opensource.org/licenses/MIT
[pedantic_link]: https://github.com/dart-lang/pedantic
[pub_badge]: https://img.shields.io/badge/even%20better%20analysis-8602C9
[pub_badge_link]: https://pub.dartlang.org/packages/even_better_analysis

