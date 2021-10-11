# Convenience scripts for i3/Sway

For scripts with more elaborate features, see [i3-new-split-long](https://github.com/mreppen/i3-new-split-long) and [i3_output_back_and_forth](https://github.com/mreppen/i3_output_back_and_forth).

## move-into

Moves a window/container *into* an adjacent one:

With windows A, B, C
```
A | B
A | C
```
with C focused and A not split, `move-into left` yields
```
A | B
C | B
```
where the usual `move left` results in
```
A | C | B
```


## do-new

Runs a sway command on the next new window:

For instance, `do-new move workspace 2 && application` opens `application` on workspace 2, or `do-new move workspace 2 && application` opens it in floating mode.

The command could be any valid i3/Sway command, so `do-new move workspace 2, floating enable && application` opens application as floating on workspace 2.  The script runs `[ con_id=$ID ] command` where `$ID` is the id of the new window and `command` is the sequence of arguments to `do-new`.

