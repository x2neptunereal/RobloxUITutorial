# Video Tutorial
- Youtube : https://youtu.be/tiQDcG_FTMY ( Credit : x2Neptune )
# Source Code
**UI Creation**
```lua
local ScreenGui = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local UICorner = Instance.new("UICorner")
local TopBar = Instance.new("Folder")
local TextLabel = Instance.new("TextLabel")
local Close = Instance.new("ImageButton")
local Shadow = Instance.new("Folder")
local DropShadowHolder = Instance.new("Frame")
local DropShadow = Instance.new("ImageLabel")
local Items = Instance.new("Folder")
local ScrollingFrame = Instance.new("ScrollingFrame")
local UIListLayout = Instance.new("UIListLayout")

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

Frame.Parent = ScreenGui
Frame.AnchorPoint = Vector2.new(0.5, 0.5)
Frame.BackgroundColor3 = Color3.fromRGB(30, 30, 30)
Frame.BorderColor3 = Color3.fromRGB(0, 0, 0)
Frame.BorderSizePixel = 0
Frame.Position = UDim2.new(0.49969098, 0, 0.5, 0)
Frame.Size = UDim2.new(0, 515, 0, 294)

UICorner.CornerRadius = UDim.new(0, 5)
UICorner.Parent = Frame

TopBar.Name = "TopBar"
TopBar.Parent = Frame

TextLabel.Parent = TopBar
TextLabel.AnchorPoint = Vector2.new(0.5, 0.5)
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.BackgroundTransparency = 1.000
TextLabel.BorderColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0.5, 0, 0.0663265288, 0)
TextLabel.Size = UDim2.new(0, 515, 0, 39)
TextLabel.Font = Enum.Font.FredokaOne
TextLabel.Text = "Alchemy Hub"
TextLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
TextLabel.TextSize = 18.000

Close.Name = "Close"
Close.Parent = TopBar
Close.AnchorPoint = Vector2.new(0.5, 0.5)
Close.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
Close.BackgroundTransparency = 1.000
Close.BorderColor3 = Color3.fromRGB(0, 0, 0)
Close.BorderSizePixel = 0
Close.Position = UDim2.new(0.963106811, 0, 0.0646258518, 0)
Close.Size = UDim2.new(0, 24, 0, 24)
Close.Image = "rbxassetid://11353098054"

Shadow.Name = "Shadow"
Shadow.Parent = Frame

DropShadowHolder.Name = "DropShadowHolder"
DropShadowHolder.Parent = Shadow
DropShadowHolder.BackgroundTransparency = 1.000
DropShadowHolder.BorderSizePixel = 0
DropShadowHolder.Size = UDim2.new(1, 0, 1, 0)
DropShadowHolder.ZIndex = 0

DropShadow.Name = "DropShadow"
DropShadow.Parent = DropShadowHolder
DropShadow.AnchorPoint = Vector2.new(0.5, 0.5)
DropShadow.BackgroundTransparency = 1.000
DropShadow.BorderSizePixel = 0
DropShadow.Position = UDim2.new(0.5, 0, 0.5, 0)
DropShadow.Size = UDim2.new(1, 47, 1, 47)
DropShadow.ZIndex = 0
DropShadow.Image = "rbxassetid://6014261993"
DropShadow.ImageColor3 = Color3.fromRGB(0, 0, 0)
DropShadow.ImageTransparency = 0.500
DropShadow.ScaleType = Enum.ScaleType.Slice
DropShadow.SliceCenter = Rect.new(49, 49, 450, 450)

Items.Name = "Items"
Items.Parent = Frame

ScrollingFrame.Parent = Items
ScrollingFrame.Active = true
ScrollingFrame.AnchorPoint = Vector2.new(0.5, 1)
ScrollingFrame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
ScrollingFrame.BackgroundTransparency = 1.000
ScrollingFrame.BorderColor3 = Color3.fromRGB(0, 0, 0)
ScrollingFrame.BorderSizePixel = 0
ScrollingFrame.Position = UDim2.new(0.5009709, 0, 1, 0)
ScrollingFrame.Size = UDim2.new(0, 515, 0, 255)
ScrollingFrame.CanvasSize = UDim2.new(0, 0, 0, 94)
ScrollingFrame.ScrollBarThickness = 2

UIListLayout.Parent = ScrollingFrame
UIListLayout.HorizontalAlignment = Enum.HorizontalAlignment.Center
UIListLayout.SortOrder = Enum.SortOrder.LayoutOrder
UIListLayout.Padding = UDim.new(0, 5)

UIListLayout:GetPropertyChangedSignal('AbsoluteContentSize'):Connect(function()
    ScrollingFrame.CanvasSize = UDim2.formOffset(0,UIListLayout.AbsoluteContentSize.Y)
end)

Close.MouseButton1Click:Connect(function()
    ScreenGui.Enabled = false
end)

local add = {
    header = function(text)
        local Header = Instance.new("TextLabel")
        local Line = Instance.new("Frame")
        local Line_2 = Instance.new("Frame")

        Header.Name = "Header"
        Header.Parent = ScrollingFrame
        Header.AnchorPoint = Vector2.new(0.5, 0.5)
        Header.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Header.BackgroundTransparency = 1.000
        Header.BorderColor3 = Color3.fromRGB(0, 0, 0)
        Header.BorderSizePixel = 0
        Header.Position = UDim2.new(0.5, 0, 0.178571433, 0)
        Header.Size = UDim2.new(0, 515, 0, 27)
        Header.Font = Enum.Font.SourceSansBold
        Header.Text = tostring(text)
        Header.TextColor3 = Color3.fromRGB(0, 255, 127)
        Header.TextSize = 18.000

        Line.Name = "Line"
        Line.Parent = Header
        Line.AnchorPoint = Vector2.new(0.5, 0.5)
        Line.BackgroundColor3 = Color3.fromRGB(0, 255, 127)
        Line.BorderColor3 = Color3.fromRGB(0, 0, 0)
        Line.BorderSizePixel = 0
        Line.Position = UDim2.new(0.699999988, 0, 0.5, 0)
        Line.Size = UDim2.new(0, 100, 0, 1)

        Line_2.Name = "Line"
        Line_2.Parent = Header
        Line_2.AnchorPoint = Vector2.new(0.5, 0.5)
        Line_2.BackgroundColor3 = Color3.fromRGB(0, 255, 127)
        Line_2.BorderColor3 = Color3.fromRGB(0, 0, 0)
        Line_2.BorderSizePixel = 0
        Line_2.Position = UDim2.new(0.300000012, 0, 0.5, 0)
        Line_2.Size = UDim2.new(0, 100, 0, 1)
    end,
    text = function(text)
        local Text = Instance.new("TextLabel")

        Text.Name = "Text"
        Text.Parent = ScrollingFrame
        Text.AnchorPoint = Vector2.new(0.5, 0.5)
        Text.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Text.BackgroundTransparency = 1.000
        Text.BorderColor3 = Color3.fromRGB(0, 0, 0)
        Text.BorderSizePixel = 0
        Text.Position = UDim2.new(0.5, 0, 0.166666672, 0)
        Text.Size = UDim2.new(0, 393, 0, 21)
        Text.Font = Enum.Font.SourceSansBold
        Text.TextColor3 = Color3.fromRGB(255, 255, 255)
        Text.TextSize = 14.000
        Text.Text = tostring(text)

        return {
            new = function(newtext)
                Text.Text = tostring(newtext)
            end
        }
    end,
    button = function(text, callback)
        local Button = Instance.new("TextButton")
        local UICorner_2 = Instance.new("UICorner")
        local UIStroke = Instance.new("UIStroke")

        Button.Name = "Button"
        Button.Parent = ScrollingFrame
        Button.AnchorPoint = Vector2.new(0.5, 0.5)
        Button.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Button.BackgroundTransparency = 0.950
        Button.BorderColor3 = Color3.fromRGB(0, 0, 0)
        Button.BorderSizePixel = 0
        Button.Position = UDim2.new(0.5, 0, 0.276470602, 0)
        Button.Size = UDim2.new(0, 436, 0, 25)
        Button.Font = Enum.Font.SourceSansBold
        Button.TextColor3 = Color3.fromRGB(255, 255, 255)
        Button.TextSize = 15.000
        Button.Text = tostring(text)
        
        UICorner_2.CornerRadius = UDim.new(0, 3)
        UICorner_2.Parent = Button
        
        UIStroke.Parent = Button
        UIStroke.Transparency = 0.8
        UIStroke.Color = Color3.fromRGB(255, 255, 255);
        UIStroke.ApplyStrokeMode = Enum.ApplyStrokeMode.Border;

        Button.MouseButton1Click:Connect(callback)
    end
}
```
**Drag Frame**
```lua
function dragify(Frame, object)
    dragToggle = nil
    dragSpeed = .25
    dragInput = nil
    dragStart = nil
    dragPos = nil
    function updateInput(input)
        Delta = input.Position - dragStart
        Position =
            UDim2.new(startPos.X.Scale, startPos.X.Offset + Delta.X, startPos.Y.Scale, startPos.Y.Offset + Delta.Y)
        game:GetService("TweenService"):Create(object, TweenInfo.new(dragSpeed), {Position = Position}):Play()
    end
    Frame.InputBegan:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseButton1 or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragToggle = true
                dragStart = input.Position
                startPos = object.Position
                input.Changed:Connect(
                    function()
                        if (input.UserInputState == Enum.UserInputState.End) then
                            dragToggle = false
                        end
                    end
                )
            end
        end
    )
    Frame.InputChanged:Connect(
        function(input)
            if
                (input.UserInputType == Enum.UserInputType.MouseMovement or
                    input.UserInputType == Enum.UserInputType.Touch)
            then
                dragInput = input
            end
        end
    )
    game:GetService("UserInputService").InputChanged:Connect(
    function(input)
        if (input == dragInput and dragToggle) then
            updateInput(input)
        end
    end
    )
end

dragify(Frame, Frame)
```
**Added Items**
```lua
add.header("General")

add.text("Hello!!, How are you")

local textlabel = add.text("You cant see this?")

add.button("Change Text",function()
    textlabel.new("This is new one!")
end)


add.header("Automatic")

add.button("Test",function()
    print("GG!")
end)

add.button("Click Me",function()
    print("Stop click me.")
end)
```
