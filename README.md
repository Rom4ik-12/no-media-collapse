# no-media-collapse

[Русский](README.ru.md)

A user module for the [illogical-impulse-plugins](https://github.com/Rom4ik-12/illogical-impulse-plugins) loader.
Collapses the bar's media/resources group to its natural width when no
track is playing, so the empty "No media" slot stops hogging space.

## What it does

Toggles two lines in `modules/ii/bar/BarContent.qml`:

```qml
// off (system default — wide and fixed)
implicitWidth: root.centerSideModuleWidth

// on  (this module — collapses when no track)
implicitWidth: (root.useShortenedForm < 2 &&
                MprisController.activePlayer?.trackTitle?.length > 0)
              ? root.centerSideModuleWidth
              : leftCenterGroup.naturalImplicitWidth
```

Enable the module to get the auto-collapse behaviour back; disable to
keep the slot at full width regardless of media state.

## Install

Paste the URL into Settings → Modules → install field:

```
https://github.com/Rom4ik-12/no-media-collapse/releases/latest/download/no-media-collapse.qsmod
```

Or grab the `.qsmod` from the [releases page](https://github.com/Rom4ik-12/no-media-collapse/releases) and drop it on the picker.

## Requirements

- illogical-impulse-plugins loader **v1.4** or newer (declared via
  `requiresLoader: "1.4"`).
