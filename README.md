
```ahk
; =========================
; NovaHop Client (AHK v1)
; =========================

#NoEnv
#SingleInstance Force
SendMode Input
SetTitleMatchMode, 2

Toggle := 0
Hidden := false

; -------------------------
; GUI SETUP
; -------------------------
Gui, +AlwaysOnTop -MaximizeBox -MinimizeBox +ToolWindow
Gui, Color, 0B0F1A

Gui, Font, s20 Bold c00E5FF, Segoe UI
Gui, Add, Text, x0 w250 Center, ✦NovaHop Client✦

Gui, Font, s10 c5A6B7A, Segoe UI
Gui, Add, Text, x0 w250 Center, P = Hide GUI | Q = Toggle Wallhop

Gui, Font, s11 Bold cFF4040, Segoe UI
Gui, Add, Text, vStatusText x0 w250 Center, ● Status: OFF

Gui, Show, w260 h140, NovaClient- Follow Robil420 on roblox!

; -------------------------
; EXIT
; -------------------------
F3::ExitApp

GuiClose:
ExitApp

; -------------------------
; FUNCTIONS
; -------------------------
UpdateStatus() {
    global Toggle

    if (Toggle)
    {
        GuiControl, +c00FF00, StatusText
        GuiControl,, StatusText, ● Status: ON
    }
    else
    {
        GuiControl, +cFF4040, StatusText
        GuiControl,, StatusText, ● Status: OFF
    }
}

; -------------------------
; HOTKEYS
; -------------------------

~p::
Hidden := !Hidden
if (Hidden)
    Gui, Hide
else
{
    Gui, Show
    UpdateStatus()
}
return

~q::
Toggle := !Toggle
UpdateStatus()
return

~LButton::
if (Toggle)
{
    MouseGetPos, , y
    MouseMove, 600, %y%
    Sleep, 50
    MouseMove, 700, %y%
}
return
```
