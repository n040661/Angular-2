## Change Detection Constants <span style='float:right;font-size:12px;line-height:40px;'>4/21/2017 1:22:43 PM </span>

### ChangeDetectionStrategy

Describes within the change detector which strategy will be used the next time change detection is triggered.

- OnPush = 0

`OnPush` means that the change detector's mode will be set to `CheckOnce` during hydration.

- Default = 1

`Default` means that the change detector's mode will be set to `CheckAlways` during hydration

### ChangeDetectorStatus

Describes the status of the detector

- CheckOnce = 0

`CheckedOnce` means that after calling detectChanges the mode of the change detector will become `Checked`.

- Checked = 1

`Checked` means that the change detector should be skipped until its mode changes to `CheckOnce`

- CheckAlways = 2

`CheckAlways` means that after calling detectChanges the mode of the change detector will remain `CheckAlways`

- Detached = 3

`Detached` means that the change detector sub tree is not a part of the main tree and should be skipped

- Errored = 4

`Errored` means that the change detector encountered an error checking a binding or calling a directive lifecycle method and is now in an inconsistent state. Change detectors in this state will no longer detect changes.

- Destroyed = 5

`Destroyed` means that the change detector is destroyed