# easyDialog (RaP-SoR / open.mp)

Named dialogs for SA:MP / open.mp, based on
[devbluen/easyDialog](https://github.com/devbluen/easyDialog) `1.0.4`
(protections + `Dialog_ReShow`), originally from Awsomedude / Emmet_.

## Install (sampctl)

```
sampctl install RaP-SoR/easyDialog:1.1.0
```

Requires YSI (`y_hooks`, `y_va`). Include YSI **before** `<easyDialog>`.

## open.mp notes

This fork silences modern `pawncc` / open.mp warnings that reappear after every
`sampctl ensure` when patching locally:

- forward declarations for tagged returns (`bool:`, `DIALOG_STYLE:`)
- renamed locals that shadowed globals (`status` → `created_status`, `string` → `haystack`)

## API

```pawn
Dialog_Show(playerid, Name, DIALOG_STYLE_LIST, "title", "body", "OK", "Cancel");

Dialog:Name(playerid, response, listitem, inputtext[]) {
    return 1;
}

Dialog_ReShow(playerid, "optional error line");
Dialog_Close(playerid);
Dialog_Created(playerid);
```

## Credits

- Emmet_ / Awsomedude — original easyDialog
- devbluen — protections and `Dialog_ReShow`
- RaP-SoR — open.mp / sampctl packaging
