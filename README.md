# Wallhop-NOVA-CLIENT
You have to doawnload Autohotkey in Microsoft store or Online. Then make a new Hotkey script and Edit the script i gave! FOLLOW Robil420 On roblox for more Clients! Here is the ✦NovaHop Client✦ Script: 


#NoEnv
#SingleInstance Force
SendMode Input
SetTitleMatchMode, 2

Toggle := 0
Hidden := false

Gui, +AlwaysOnTop -MaximizeBox -MinimizeBox +ToolWindow
Gui, Color, 0B0F1A

Gui, Font, s20 Bold c00E5FF, Segoe UI
Gui, Add, Text, x0 w250 Center, ✦NovaHop Client✦

Gui, Font, s10 c5A6B7A, Segoe UI
Gui, Add, Text, x0 w250 Center, Press P to Hide Gui / Press Q to turn Wallhop On!

Gui, Font, s11 Bold cFF4040, Segoe UI
Gui, Add, Text, vStatusText x0 w250 Center, ● Status: OFF

Gui, Show, w260 h140, NOVA Client

F3::ExitApp

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

GuiClose:
ExitApp
