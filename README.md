# UI
Credits to Vep on the RobloxScripts Forum.

Original post:
https://forum.robloxscripts.com/showthread.php?tid=1716

This is not my UI library, I'm only making this functional to use for scripts.

:)

Here's some functions in the UI, since there's not really any posts about it.

Main UI Code:
local lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/v60x/UI/main/Main"))()

Add a window to the UI. (This will be the text at the top of the UI) The KeyCode is which button you want used to hide/show the UI.
local win = lib:Window("PREVIEW",Color3.fromRGB(44, 120, 224), Enum.KeyCode.RightControl)

Add a tab. (Can be multiple.)
local tab = win:Tab("Tab 1")

Button function that fires your script of choice. (Example function: printing a message.)
tab:Button("Button", function()
    print("Pressed!")
end)

Add a notification to a button, slider, toggle, etc.
lib:Notification("Notification", "Hello!", "Hi!")

Example of a notification being used:
tab:Button("Button", function()
    lib:Notification("Notification", "This is an example message.", "Okay!")
end)

Example of a toggle. (False is what it the value is once the UI is executed. If you want the toggle to be on, then change false to true.)
tab:Toggle("Toggle",false, function(t)
    print(t)
end)

Example of a slider. You can change this to walkspeed like every other UI does, or simply just change it to whatever.
tab:Slider("Slider",0,100,30, function(t)
    print(t)
end)

Example of a dropdown. (This explains itself.)
tab:Dropdown("Dropdown",{"Option 1","Option 2","Option 3","Option 4","Option 5"}, function(t)
    print(t)
end)

Color picker (Changes the color of the UI.)
tab:Colorpicker("Colorpicker",Color3.fromRGB(255,0,0), function(t)
    print(t)
end)

Example of a textbox. (Input custom values into the textbox, more tricky for starters imo)
tab:Textbox("Textbox",true, function(t)
    print(t)
end)

Toggle a script with a keybind. (Good for ESP, AutoRob, etc.)
tab:Bind("Bind",Enum.KeyCode.RightShift, function()
    print("Pressed!")
end)

A pre-made tab for changing UI color. (Use this if you'd like. Saves your troubles.)
local changeclr = win:Tab("Change UI Color")

changeclr:Colorpicker("Change UI Color",Color3.fromRGB(44, 120, 224), function(t)
    lib:ChangePresetColor(Color3.fromRGB(t.R * 255, t.G * 255, t.B * 255))
end)
