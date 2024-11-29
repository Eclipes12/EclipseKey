-- ModuleScript: CustomUI
local CustomUI = {}
CustomUI.__index = CustomUI

-- Theme Settings
CustomUI.Theme = {
    BackgroundColor = Color3.fromRGB(30, 30, 30),
    ButtonColor = Color3.fromRGB(45, 45, 45),
    TextColor = Color3.fromRGB(255, 255, 255),
    CornerRadius = UDim.new(0, 5)
}

-- Utility function to create UI elements
local function create(instanceType, properties)
    local instance = Instance.new(instanceType)
    for prop, value in pairs(properties) do
        instance[prop] = value
    end
    return instance
end

-- Create a new window
function CustomUI:CreateWindow(title)
    local screenGui = create("ScreenGui", {Name = "CustomUI", Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")})
    local mainFrame = create("Frame", {
        Parent = screenGui,
        Size = UDim2.new(0, 400, 0, 300),
        BackgroundColor3 = self.Theme.BackgroundColor,
        AnchorPoint = Vector2.new(0.5, 0.5),
        Position = UDim2.new(0.5, 0, 0.5, 0)
    })
    
    local uiCorner = create("UICorner", {
        Parent = mainFrame,
        CornerRadius = self.Theme.CornerRadius
    })
    
    local titleLabel = create("TextLabel", {
        Parent = mainFrame,
        Size = UDim2.new(1, 0, 0, 30),
        BackgroundTransparency = 1,
        Text = title,
        TextColor3 = self.Theme.TextColor,
        Font = Enum.Font.SourceSansBold,
        TextSize = 20
    })

    return {
        Frame = mainFrame,
        Title = titleLabel
    }
end

-- Add a button
function CustomUI:AddButton(parent, buttonText, callback)
    local button = create("TextButton", {
        Parent = parent,
        Size = UDim2.new(1, -20, 0, 40),
        Position = UDim2.new(0, 10, 0, 50),
        BackgroundColor3 = self.Theme.ButtonColor,
        Text = buttonText,
        TextColor3 = self.Theme.TextColor,
        Font = Enum.Font.SourceSans,
        TextSize = 18
    })

    local uiCorner = create("UICorner", {
        Parent = button,
        CornerRadius = self.Theme.CornerRadius
    })

    button.MouseButton1Click:Connect(function()
        if callback then callback() end
    end)
end

return CustomUI
