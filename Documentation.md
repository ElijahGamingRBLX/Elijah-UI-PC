# Elijah UI PC
This documentation is for Elijah UI PC Credit To Me

## Booting the Elijah UI PC Library
```lua
local library = loadstring(game:HttpGet("https://raw.githubusercontent.com/ElijahGamingRBLX/Elijah-UI-PC/main/library.lua"))()
```




## Creating a Elijah UI PC Window
```lua
local elijahuipc = library.new("Elijah UI PC", 5013109572)
```

## Creating a Tab
```lua
local page = elijahuipc:addPage("Test", 5012544693)
```

## Creating a Section
```lua
local section1 = page:addSection("Section 1")
```

## Creating a Button
```lua
section1:addButton("Button", function()
print("Clicked")
end)
```

## Creating a Toggle
```lua
section1:addToggle("Toggle", nil, function(value)
print("Toggled", value)
end)
```

## Creating a Textbox
```lua
section1:addTextbox("Notification", "Default", function(value, focusLost)
print("Input", value)
```

## Creating a Notification
```lua
elijahuipc:Notify("Title", value)
end
end)
```

## Creating a Keybind
```lua
section2:addKeybind("Toggle Keybind", Enum.KeyCode.One, function()
print("Activated Keybind")
elijahuipc:toggle()
end, function()
print("Changed Keybind")
end)
```

## Creating a Colorpicker
```lua
section2:addColorPicker("ColorPicker", Color3.fromRGB(50, 50, 50))
section2:addColorPicker("ColorPicker2")
```

## Creating a Slider
```lua
section2:addSlider("Slider", 0, -100, 100, function(value)
print("Dragged", value)
end)
```

## Creating a Dropdown
```lua
section2:addDropdown("Dropdown", {"Hello", "World", "Hello World", "Word", 1, 2, 3}, function(text)
   print("Selected", text)
end)
```

## Creating a Color Theme
```lua
local theme = elijahuipc:addPage("Theme", 5012544693)
local colors = theme:addSection("Colors")

for theme, color in pairs(themes) do -- all in one theme changer, i know, im cool
colors:addColorPicker(theme, color, function(color3)
elijahuipc:setTheme(theme, color3)
end)
end
```

## Creating The Load UI
```lua
elijahuipc:SelectPage(elijahuipc.pages[1], true) -- no default for more freedom
```
