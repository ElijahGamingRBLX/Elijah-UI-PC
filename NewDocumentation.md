# Elijah UI PC [UPDATED]
This documentation is for Elijah UI PC Credit To Me

## Booting the Elijah UI PC Library
```lua
local ElijahUIPC = loadstring(game:HttpGet("https://raw.githubusercontent.com/ElijahGamingRBLX/Elijah-UI-PC/main/newlibrary.lua"))()
```




## Creating a Elijah UI PC Window
```lua
local UI = ElijahUIPC.new({
    title = "Elijah UI"
})
```

## Creating a Theme
```lua
local Themes = {
    Background = Color3.fromRGB(24, 24, 24),
    Glow = Color3.fromRGB(0, 0, 0),
    Accent = Color3.fromRGB(10, 10, 10),
    LightContrast = Color3.fromRGB(20, 20, 20),
    DarkContrast = Color3.fromRGB(14, 14, 14),  
    TextColor = Color3.fromRGB(255, 255, 255)
}
```

## Creating a Tab
```lua
local Test = UI:addPage({
    title = "Hi",
    icon = 5012544693
})
```

## Creating a Section
```lua
local SectionA = Test:addSection({
    title = "Section A"
})
```

## Creating a Toggle
```lua
SectionA:addToggle({
    title = "Toggle",
    callback = function(value)
        print("Toggled", value)
    end
})
```

## Creating a Button
```lua
SectionA:addButton({
    title = "Button",
    callback = function()
        print("Clicked")
    end
})
```

## Creating a Textbox
```lua
SectionA:addTextbox({
    title = "Notification",
    default = "Default",
    callback = function(value, focusLost)
        print("Input", value)

        if (focusLost) then
            UI:Notify({
                title = "Title",
                text = value
            })
        end
    end
})
```

## Creating a Keybind
```lua
SectionB:addKeybind({
    title = "Toggle Keybind",
    key = Enum.KeyCode.One,
    callback = function()
        print("Activated Keybind")
        UI:toggle()
    end,
    changedCallback = function(key)
        print("Changed Keybind", key)
    end
})
```

## Creating a Colorpicker
```lua
SectionB:addColorPicker({
    title = "ColorPicker",
    default = Color3.fromRGB(50, 50, 50)
})

SectionB:addColorPicker({
    title = "ColorPicker2"
})
```

## Creating a Slider
```lua
SectionB:addSlider({
    title = "Slider",
    default = 0,
    min = -100,
    max = 100,
    callback = function(value)
        print("Dragged", value)
    end
})
```

## Creating a Dropdown Content
```lua
local dropdownContent = {"Hello", "World", "Hello World", "Word", 1, 2, 3} -- // To save me from keep on doing this
SectionB:addDropdown({
    title = "Dropdown",
    list = dropdownContent
})
```

## Creating a Dropdown
```lua
SectionB:addDropdown({
    title = "Dropdown",
    list = dropdownContent,
    callback = function(text)
        print("Selected", text)
    end
})
```

## Creating a Local Theme
```lua
local Theme = UI:addPage({
    title = "Theme",
    icon = 5012544693
})
```

## Creating a Section Theme
```lua
local Colors = Theme:addSection({
    title = "Colors"
})
```

## Creating Add Colorpicker
```lua
for theme, color in pairs(Themes) do
    Colors:addColorPicker({
        title = theme,
        default = color,
        callback = function(color3)
            UI:setTheme({
                theme = theme, 
                color3 = color3
            })
        end
    })
end
```

## Creating The UI Load
```lua
UI:SelectPage({
    page = UI.pages[1], 
    toggle = true
})
```
