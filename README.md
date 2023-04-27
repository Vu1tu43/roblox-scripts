# Vapor UI Library API document by Vulture#1759

> This UI lib makes it so memory checks don't work, once executing it hooks a function to gcinfo and collectgarbage, returning a real looking value between 200 and 350.

## Creating a new UI

```
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/Vu1tu43/roblox-scripts/main/ui-lib.lua"))
local newUI = library:New(title,ver)
```

## Creating a new frame

> This function uses three vars:
> name - for the page name & button text
> icon - for the button's icon
> title - for where the button goes on the sidebar under a title

```
local newFrame = library:NewFrame(name,icon,title)
```

## Creating a new section

> Creates a section on the given frame

```
local newSection = newFrame:NewSection(title)
```

## Creating a new Toggle

> returns true/false

```
newSection:NewToggle(name,desc,default,function)
```

## Creating a new slider

> returns a number, depending on where the slider is

```
newSection:NewSlider(name,desc,min,max,function)
```

## Creating a new button

> its just a button

```
newSection:NewButton(name,desc,function)
```

## Creating a new keybind

> Default must be an enum (look below for example)

```
newSection:NewKeybind(name,desc,default,function)
```

## Creating a new DropDown

> Returns the clicked option

```
newSection:NewDropDown(name,desc,options,function)
```

## Getting the exploit name

> Works for most exploits

```
local Executor = library:detectExploit()
```

## Creating a new notification

> Max of 4 options
> Max length of 5 chars per option

> With callback (returns clicked button's name)

```
library:Notify(name,desc,buttons,extra,function)
```

> Without callback

```
library:Notify(name,desc,buttons,extra)
```

## Destroying the UI

> it just removes the UI completely

```
library:DestroyGUI()
```

## Once finished it should look like this

> This is an example

```
local lib = loadstring(game:HttpGet("https://raw.githubusercontent.com/Vu1tu43/roblox-scripts/main/ui-lib.lua"))
local newUI = lib:New("Vapor UI LIB Example", "v1")
local newFrame = lib:NewFrame("newFrame/Title", "rbxassetid://90272641","Main")
local newSection = newFrame:NewSection("pooper")
local Executor = b:detectExploit()

newSection:NewToggle("toggle", "description", false, function(a)
    print(a)
end)
newSection:NewSlider("slider","description",1,100,function(a)
    print(a)
end)
newSection:NewButton("button", "description",function()
    print("button clicked")
end)
newSection:NewKeybind("keybind","description",Enum.KeyCode.F,function()
    print("keybind clicked")
end)
newSection:NewDropDown("dropdown","description",{
    "hi",
    "bye",
    "piss"
}, function(c)
    print(c)
end)
```
