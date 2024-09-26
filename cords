local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoid = character:FindFirstChildOfClass("Humanoid")
local rootPart = character:FindFirstChild("HumanoidRootPart")

-- Создаем GUI
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = player.PlayerGui
screenGui.Name = "PlayerCoordinates"

local frame = Instance.new("Frame")
frame.Parent = screenGui
frame.Size = UDim2.new(0.15, 0, 0.1, 0)
frame.Position = UDim2.new(0.8, 0, 0.5, 0)
frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
frame.BorderColor3 = Color3.fromRGB(0, 0, 0)

local textLabel = Instance.new("TextLabel")
textLabel.Parent = frame
textLabel.Size = UDim2.new(0.8, 0, 0.5, 0)
textLabel.Text = "Cords: (0, 0, 0)"
textLabel.BackgroundTransparency = 1
textLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
textLabel.TextSize = 14
textLabel.Position = UDim2.new(0.1, 0, 0.1, 0)

local hideButton = Instance.new("TextButton")
hideButton.Parent = frame
hideButton.Text = "Hide"
hideButton.Size = UDim2.new(0.4, 0, 0.3, 0)
hideButton.BackgroundColor3 = Color3.fromRGB(220, 220, 220)
hideButton.TextColor3 = Color3.fromRGB(0, 0, 0)
hideButton.TextSize = 14
hideButton.Position = UDim2.new(0.1, 0, 0.6, 0)

local updateButton = Instance.new("TextButton")
updateButton.Parent = frame
updateButton.Text = "Update"
updateButton.Size = UDim2.new(0.4, 0, 0.3, 0)
updateButton.BackgroundColor3 = Color3.fromRGB(220, 220, 220)
updateButton.TextColor3 = Color3.fromRGB(0, 0, 0)
updateButton.TextSize = 14
updateButton.Position = UDim2.new(0.5, 0, 0.6, 0)

local function updatePosition()
  local position = rootPart.Position
  textLabel.Text = "Cords: (" .. math.floor(position.X) .. ", " .. math.floor(position.Y) .. ", " .. math.floor(position.Z) .. ")"
end

local function hideGUI()
  screenGui.Enabled = false
end

local function showGUI()
  screenGui.Enabled = true
end

rootPart.Changed:Connect(function(property)
  if property == "Position" then
    updatePosition()
  end
end)

updatePosition()

hideButton.MouseButton1Click:Connect(function()
  if screenGui.Enabled then
    hideGUI()
    hideButton.Text = "Show"
  else
    showGUI()
    hideButton.Text = "Hide"
  end
end)

updateButton.MouseButton1Click:Connect(updatePosition)
