local ScreenGui = Instance.new("ScreenGui")
local MainFrame = Instance.new("Frame")
local ScriptBox = Instance.new("TextBox")
local RunButton = Instance.new("TextButton")
local ClearButton = Instance.new("TextButton")
local MainMenuButton = Instance.new("TextButton")
local InfoButton = Instance.new("TextButton")
local ScriptsButton = Instance.new("TextButton")
local HideButton = Instance.new("TextButton")
local ResizeButton = Instance.new("TextButton")
local MiniFrame = Instance.new("Frame")

local InfoLabel = Instance.new("TextLabel")
local PlayerNameLabel = Instance.new("TextLabel")
local FPSLabel = Instance.new("TextLabel")
local PingLabel = Instance.new("TextLabel")
local DeveloperLabel = Instance.new("TextLabel")

-- إعداد واجهة المستخدم
ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")

-- إعداد الإطار الرئيسي
MainFrame.Parent = ScreenGui
MainFrame.Size = UDim2.new(0.6, 0, 0.5, 0)
MainFrame.Position = UDim2.new(0.2, 0, 0.25, 0)
MainFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MainFrame.Active = true
MainFrame.Draggable = true  -- تفعيل السحب للواجهة

-- إعداد صندوق النص
ScriptBox.Parent = MainFrame
ScriptBox.Size = UDim2.new(0.6, 0, 0.4, 0)
ScriptBox.Position = UDim2.new(0.05, 0, 0.1, 0)
ScriptBox.PlaceholderText = "اكتب سكربت Lua هنا"
ScriptBox.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ScriptBox.TextColor3 = Color3.fromRGB(255, 255, 255)
ScriptBox.BorderColor3 = Color3.fromRGB(0, 0, 255)

-- إعداد الأزرار الجانبية
local buttons = {MainMenuButton, InfoButton, ScriptsButton}
local buttonTexts = {"القائمة الرئيسية", "المعلومات", "السكربتات"}
for i, button in ipairs(buttons) do
    button.Parent = MainFrame
    button.Size = UDim2.new(0.25, 0, 0.1, 0)
    button.Position = UDim2.new(0.7, 0, 0.1 * (i - 1) + 0.1, 0)
    button.Text = buttonTexts[i]
    button.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
    button.TextColor3 = Color3.fromRGB(255, 255, 255)
    button.BorderColor3 = Color3.fromRGB(0, 0, 255)
end

-- زر التشغيل
RunButton.Parent = MainFrame
RunButton.Size = UDim2.new(0.3, 0, 0.1, 0)
RunButton.Position = UDim2.new(0.1, 0, 0.6, 0)
RunButton.Text = "تشغيل"
RunButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
RunButton.TextColor3 = Color3.fromRGB(255, 255, 255)
RunButton.BorderColor3 = Color3.fromRGB(0, 0, 255)

-- زر حذف الكود
ClearButton.Parent = MainFrame
ClearButton.Size = UDim2.new(0.3, 0, 0.1, 0)
ClearButton.Position = UDim2.new(0.5, 0, 0.6, 0)
ClearButton.Text = "حذف الكود"
ClearButton.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
ClearButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ClearButton.BorderColor3 = Color3.fromRGB(0, 0, 255)

-- زر الإخفاء
HideButton.Parent = MainFrame
HideButton.Size = UDim2.new(0.1, 0, 0.1, 0)
HideButton.Position = UDim2.new(0.9, -5, 0, 5)
HideButton.Text = "X"
HideButton.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
HideButton.TextColor3 = Color3.fromRGB(255, 255, 255)

-- زر تغيير الحجم
ResizeButton.Parent = MainFrame
ResizeButton.Size = UDim2.new(0.1, 0, 0.1, 0)
ResizeButton.Position = UDim2.new(0.9, -5, 0.9, -5)
ResizeButton.Text = "⇔"
ResizeButton.BackgroundColor3 = Color3.fromRGB(0, 0, 255)
ResizeButton.TextColor3 = Color3.fromRGB(255, 255, 255)

-- المربع المصغر للإظهار
MiniFrame.Parent = ScreenGui
MiniFrame.Size = UDim2.new(0.1, 0, 0.1, 0)
MiniFrame.Position = UDim2.new(0, 10, 0, 10)
MiniFrame.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
MiniFrame.Visible = false

local ShowButton = Instance.new("TextButton")
ShowButton.Parent = MiniFrame
ShowButton.Size = UDim2.new(1, 0, 1, 0)
ShowButton.Text = "◄"
ShowButton.TextColor3 = Color3.fromRGB(255, 255, 255)
ShowButton.BackgroundTransparency = 1

-- إعداد التسميات المعلوماتية
InfoLabel.Parent = MainFrame
InfoLabel.Size = UDim2.new(0.6, 0, 0.05, 0)
InfoLabel.Position = UDim2.new(0.05, 0, 0, 0)
InfoLabel.Text = "المعلومات"
InfoLabel.BackgroundTransparency = 1
InfoLabel.TextColor3 = Color3.fromRGB(255, 255, 255)

PlayerNameLabel.Parent = MainFrame
PlayerNameLabel.Size = UDim2.new(0.6, 0, 0.05, 0)
PlayerNameLabel.Position = UDim2.new(0.05, 0, 0.1, 0)
PlayerNameLabel.BackgroundTransparency = 1
PlayerNameLabel.TextColor3 = Color3.fromRGB(255, 255, 255)

FPSLabel.Parent = MainFrame
FPSLabel.Size = UDim2.new(0.6, 0, 0.05, 0)
FPSLabel.Position = UDim2.new(0.05, 0, 0.15, 0)
FPSLabel.BackgroundTransparency = 1
FPSLabel.TextColor3 = Color3.fromRGB(255, 255, 255)

PingLabel.Parent = MainFrame
PingLabel.Size = UDim2.new(0.6, 0, 0.05, 0)
PingLabel.Position = UDim2.new(0.05, 0, 0.2, 0)
PingLabel.BackgroundTransparency = 1
PingLabel.TextColor3 = Color3.fromRGB(255, 255, 255)

-- مربع معلومات المطور
DeveloperLabel.Parent = MainFrame
DeveloperLabel.Size = UDim2.new(0.6, 0, 0.05, 0)
DeveloperLabel.Position = UDim2.new(0.3, 0, 0.3, 0)
DeveloperLabel.Text = "المطور: KA_KILLR"
DeveloperLabel.BackgroundColor3 = Color3.fromRGB(50, 50, 50)
DeveloperLabel.TextColor3 = Color3.fromRGB(255, 255, 255)
DeveloperLabel.BorderColor3 = Color3.fromRGB(0, 0, 255)

-- إظهار المعلومات
InfoButton.MouseButton1Click:Connect(function()
    ScriptBox.Visible = false
    InfoLabel.Visible = true
    PlayerNameLabel.Visible = true
    FPSLabel.Visible = true
    PingLabel.Visible = true
    DeveloperLabel.Visible = true

    PlayerNameLabel.Text = "اسم اللاعب: " .. game.Players.LocalPlayer.Name
    FPSLabel.Text = "عدد الفريمات: " .. tostring(workspace:GetRealPhysicsFPS())
    PingLabel.Text = "البنك: " .. tostring(game:GetService("Stats").Network.ServerStatsItem["Data Ping"]:GetValue())
end)

-- تشغيل وإخفاء الواجهة
HideButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = false
    MiniFrame.Visible = true
end)

ShowButton.MouseButton1Click:Connect(function()
    MainFrame.Visible = true
    MiniFrame.Visible = false
end)

-- تشغيل الكود
RunButton.MouseButton1Click:Connect(function()
    local scriptCode = ScriptBox.Text
    loadstring(scriptCode)()  -- تشغيل الكود
end)

-- حذف الكود
ClearButton.MouseButton1Click:Connect(function()
    ScriptBox.Text = ""
end)
