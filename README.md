# Wallhop-NOVA-CLIENT
You have to doawnload Autohotkey in Microsoft store or Online. Then make a new Hotkey script and Edit the script i gave! FOLLOW Robil420 On roblox for more Clients! Here is the ✦NovaHop Client✦ Script: #NoEnv
#SingleInstance Force
SendMode Input
SetTitleMatchMode, 2

Toggle := 0
Hidden := false

; ===== GUI =====
Gui, +AlwaysOnTop -MaximizeBox -MinimizeBox +ToolWindow
Gui, Color, 0B0F1A

Gui, Font, s20 Bold c00E5FF, Segoe UI
Gui, Add, Text, x0 w250 Center, ✦NovaHop Client✦

Gui, Font, s10 c5A6B7A, Segoe UI
Gui, Add, Text, x0 w250 Center, Press P to Hide Gui / Press Q to turn Wallhop On!

Gui, Font, s11 Bold cFFFFFF, Segoe UI
Gui, Add, Text, vStatusText x0 w250 Center, ● Status: OFF

Gui, Font, s9 c3A4A66, Segoe UI
Gui, Add, Text, vHint x0 w250 Center, P = Hide | Q = Toggle

Gui, Add, Text, x10 w230 h1 Background00E5FF

Gui, Show, w260 h140, NOVA Client- Follow Robil420 on Roblox!

; ===== HOTKEYS =====

F3::ExitApp

; P = hide/show GUI
~p::
Hidden := !Hidden

if (Hidden)
    Gui, Hide
else
    Gui, Show
return

; Q = toggle
~q::
Toggle := !Toggle

; keine Notifications wenn hidden
if (!Hidden)
{
    TrayTip
    Sleep, 50

    if (Toggle)
    {
        GuiControl, +c00FF00, StatusText
        GuiControl,, StatusText, Status: ON
        TrayTip, WALLHOP, WALLHOP ON, 1
    }
    else
    {
        GuiControl, +cFF4040, StatusText
        GuiControl,, StatusText, Status: OFF
        TrayTip, WALLHOP, WALLHOP OFF, 1
    }
}
else
{
    ; nur intern updaten
    if (Toggle)
        GuiControl,, StatusText, Status: ON
    else
        GuiControl,, StatusText, Status: OFF
}
return

; ===== WALLHOP =====

~LButton::
if (Toggle)
{
    SetDefaultMouseSpeed, 1

    MouseGetPos, , y
    MouseMove, 600, %y%
    Sleep, 50

    MouseGetPos, , y
    MouseMove, 700, %y%
}
return

GuiClose:
ExitApp
