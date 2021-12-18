	game.StarterGui:SetCore("SendNotification", {
		Title = "BorkWare"; 
		Text = "Welcome " .. game.Players.LocalPlayer.Name ..  " Thanks For Using BorkWare!";
		Duration = 5; 
	})
	

local Services = setmetatable({
LocalPlayer = game:GetService("Players").LocalPlayer,
Camera = workspace.CurrentCamera,
}, {
__index = function(self, idx)
return rawget(self, idx) or game:GetService(idx)
end
})

local Funcs = {}

function Funcs:Round(number)
return math.floor(tonumber(number) + 0.5)
end


function Funcs:IsAlive(player)
if player and player.Character and player.Character:FindFirstChild("Head") and workspace:FindFirstChild(player.Character.Name) and player ~= Services.LocalPlayer then
return true
end
end

function Funcs:DrawSquare()
local Box = Drawing.new("Square")
Box.Color = Color3.fromRGB(190, 190, 0)
Box.Thickness = 0.5
Box.Filled = false
Box.Transparency = 1
return Box
end

function Funcs:DrawQuad() -- Unused
local quad = Drawing.new("Quad")
quad.Color = Color3.fromRGB(190, 190, 0)
quad.Thickness = 0.5
quad.Filled = false
quad.Transparency = 1
return quad
end

function Funcs:DrawLine()
local line = Drawing.new("Line")
line.Color = Color3.new(190, 190, 0)
line.Thickness = 0.5
return line
end

function Funcs:DrawText()
local text = Drawing.new("Text")
text.Color = Color3.fromRGB(190, 190, 0)
text.Size = 20
text.Outline = true
text.Center = true
return text
end
local Config = {
	WindowName = "BorkWare - The Best Hub for Shit Games",
	Color = Color3.fromRGB(255,128,64),
	Keybind = Enum.KeyCode.RightShift,

}

 Settings = {
       Toggles = {
        Silent = false,
        FOV = 100,
        DrawFOV = false,
        Distance = math.huge,
        Accuracy = 100,
        Construct = false,
        CAuraSize = 10,
        BoxEsp = false, 
        EnemyColor = Color3.fromRGB(196, 40, 28),
        TeamColor = Color3.fromRGB(75, 151, 75),
        WalkSpeed = 16,
        JumpPower = 50
    }
}
local Library = loadstring(game:HttpGet("https://raw.githubusercontent.com/Ihaveash0rtnamefordiscord/Releases/main/AlexR32CSGO"))()
local Window = Library:CreateWindow(Config, game:GetService("CoreGui"))

local Tab1 = Window:CreateTab("Main")
local Tab4 = Window:CreateTab("Visual")
local Tab2 = Window:CreateTab("Settings")


local Visual = Tab4:CreateSection("Visuals")
local Section1 = Tab1:CreateSection("Combat")
local SectionUwU = Tab1:CreateSection("Character")
local Extra = Tab1:CreateSection("Extra")

local Section3 = Tab2:CreateSection("Menu")
local Section4 = Tab2:CreateSection("Background")
local Credits = Tab2:CreateSection("Credits")

SectionUwU:CreateSlider("WalkSpeed",16,100,nil,false, function(Value)
Settings.Toggles.WalkSpeed = Value
end)

SectionUwU:CreateSlider("JumpPower",50,100,nil,false, function(Value)
Settings.Toggles.JumpPower = Value
end)

Extra:CreateToggle("Construct Aura", nil, function(State)
Settings.Toggles.Construct = State
end)
Extra:CreateSlider("Construct Aura Size",0,20,nil,false, function(Value)
Settings.Toggles.CAuraSize = Value
end)
Section1:CreateToggle("Silent-Aim", nil, function(State)
Settings.Toggles.Silent = State
end)

Visual:CreateToggle("Box Esp", nil, function(State)
Settings.Toggles.BoxEsp = State
end)
Visual:CreateColorpicker("Enemy Color", function(Color)
Settings.Toggles.EnemyColor = Color
end)
Visual:CreateColorpicker("Team Color", function(Color)
Settings.Toggles.TeamColor = Color
end)

Section1:CreateSlider("Silent-Aim Accuracy",0,100,nil,false, function(Value)
Settings.Toggles.Distance = Value
end)

Section1:CreateSlider("Max Target Distance",0,100000,nil,false, function(Value)
Settings.Toggles.Distance = Value
end)

Section1:CreateSlider("FOV",0,2500,nil,false, function(Value)
Settings.Toggles.FOV = Value
end)
Section1:CreateToggle("Draw FOV", nil, function(State)
Settings.Toggles.DrawFOV = State
end)


local FOVCircle = Drawing.new("Circle")
FOVCircle.Color = Color3.fromRGB(190, 190, 0)
FOVCircle.Thickness = 0.5
FOVCircle.NumSides = 16
FOVCircle.Filled = false
FOVCircle.Transparency = 1

   game:GetService("RunService").RenderStepped:Connect(function()
       if  game:GetService("Players").LocalPlayer.PlayerScripts.LocalMain.Bindables.CharacterAdded:FindFirstChild("AntiExploit") then
      game:GetService("Players").LocalPlayer.PlayerScripts.LocalMain.Bindables.CharacterAdded.AntiExploit:Destroy()
  end
    if  game:GetService("Players").LocalPlayer.PlayerScripts.LocalMain.GeneralFunctions:FindFirstChild("KickPlayer") then
      game:GetService("Players").LocalPlayer.PlayerScripts.LocalMain.GeneralFunctions.KickPlayer:Destroy()
    end  
if game.Players.LocalPlayer.Character:FindFirstChild("Humanoid") then
game.Players.LocalPlayer.Character.Humanoid.JumpPower = Settings.Toggles.JumpPower
game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Settings.Toggles.WalkSpeed
game.Players.LocalPlayer.Character.Humanoid:GetPropertyChangedSignal("WalkSpeed"):Connect(function()
    game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = Settings.Toggles.WalkSpeed
    end)
end
if Settings.Toggles.Construct then
    for _,v in pairs(game:GetService("Workspace").Structures:GetChildren()) do
    if v:IsA("Model") then
        if (game.Players.LocalPlayer.Character.HumanoidRootPart.Position - v:FindFirstChild("Root").Position).Magnitude < Settings.Toggles.CAuraSize then
if game.Players.LocalPlayer.Character:FindFirstChild("Build") then
game.Players.LocalPlayer.Character.Build.Work:FireServer(v)
end
end
end
end
end
FOVCircle.Position = game:GetService('UserInputService'):GetMouseLocation();
FOVCircle.Radius = Settings.Toggles.FOV
if Settings.Toggles.DrawFOV then
FOVCircle.Visible = true
else
FOVCircle.Visible = false
end
end)

Section1:CreateColorpicker("FOV Color", function(Color)
FOVCircle.Color = Color
end)

local Mouse = game:GetService('Players').LocalPlayer:GetMouse()
function GetTarget()
   local Plr = nil
   local SD = math.huge
       for i, v in pairs(game:GetService('Players'):GetPlayers()) do
           if v ~= game.Players.LocalPlayer and v.Character and v.Character:FindFirstChild('Head') and v.Character:FindFirstChild('Humanoid') then
               if v.Team ~= game:GetService('Players').LocalPlayer.Team then
                   local pos = game:GetService('Workspace').CurrentCamera:WorldToViewportPoint(v.Character:FindFirstChild('HumanoidRootPart').Position)
                   local magnitude = (Vector2.new(pos.X, pos.Y) - Vector2.new(Mouse.X, Mouse.Y)).magnitude
                   if magnitude < SD and magnitude <= Settings.Toggles.FOV then
                       Plr = v
                       SD = magnitude
                   end
               end
           end
       end  
   return Plr
end

local OldNamecall
OldNamecall = hookmetamethod(game, "__namecall", function(self, ...)
       local args = {...}
       local method = getnamecallmethod()

       if tostring(self) == "ShootEvent" and method == "FireServer" and Settings.Toggles.Silent and Settings.Toggles.Accuracy >= math.random(1,100) then
           args[5] = GetTarget().Character.Head
           args[6] = GetTarget().Character.Head.Position

           return self.FireServer(self, unpack(args))
end
return OldNamecall(self, ...)
end)

function Funcs:AddEsp(player)
local Box = Funcs:DrawSquare()
local Tracer = Funcs:DrawLine()
local Name = Funcs:DrawText()
local Distance = Funcs:DrawText()
local SnapLines = Funcs:DrawLine()
local HeadLowerTorso = Funcs:DrawLine()
local NeckLeftUpper = Funcs:DrawLine()
local LeftUpperLeftLower = Funcs:DrawLine()
local NeckRightUpper = Funcs:DrawLine()
local RightUpperLeftLower = Funcs:DrawLine()
local LowerTorsoLeftUpper = Funcs:DrawLine()
local LeftLowerLeftUpper = Funcs:DrawLine()
local LowerTorsoRightUpper = Funcs:DrawLine()
local RightLowerRightUpper = Funcs:DrawLine()
local bottomrightone = Funcs:DrawLine()
local bottomleftone = Funcs:DrawLine()
local toprightone = Funcs:DrawLine()
local topleftone = Funcs:DrawLine()
local toplefttwo = Funcs:DrawLine()
local bottomlefttwo = Funcs:DrawLine()
local toprighttwo = Funcs:DrawLine()
local bottomrighttwo = Funcs:DrawLine()
Services.RunService.Stepped:Connect(function()
    if player.Team == Services.LocalPlayer.Team then
  Box.Color = Settings.Toggles.TeamColor
  Tracer.Color = Settings.Toggles.TeamColor
  HeadLowerTorso.Color = Settings.Toggles.TeamColor
  NeckLeftUpper.Color = Settings.Toggles.TeamColor
  LeftUpperLeftLower.Color = Settings.Toggles.TeamColor
  NeckRightUpper.Color = Settings.Toggles.TeamColor
  RightUpperLeftLower.Color = Settings.Toggles.TeamColor
  LowerTorsoLeftUpper.Color = Settings.Toggles.TeamColor
  LeftLowerLeftUpper.Color = Settings.Toggles.TeamColor
  LowerTorsoRightUpper.Color = Settings.Toggles.TeamColor
  RightLowerRightUpper.Color = Settings.Toggles.TeamColor
  bottomrightone.Color = Settings.Toggles.TeamColor
  bottomleftone.Color = Settings.Toggles.TeamColor
  toprightone.Color = Settings.Toggles.TeamColor
  topleftone.Color = Settings.Toggles.TeamColor
  toplefttwo.Color = Settings.Toggles.TeamColor
  bottomlefttwo.Color = Settings.Toggles.TeamColor
  toprighttwo.Color = Settings.Toggles.TeamColor
  bottomrighttwo.Color = Settings.Toggles.TeamColor
else
  Box.Color = Settings.Toggles.EnemyColor
  Tracer.Color = Settings.Toggles.EnemyColor
  HeadLowerTorso.Color = Settings.Toggles.EnemyColor
  NeckLeftUpper.Color = Settings.Toggles.EnemyColor
  LeftUpperLeftLower.Color = Settings.Toggles.EnemyColor
  NeckRightUpper.Color = Settings.Toggles.EnemyColor
  RightUpperLeftLower.Color = Settings.Toggles.EnemyColor
  LowerTorsoLeftUpper.Color = Settings.Toggles.EnemyColor
  LeftLowerLeftUpper.Color = Settings.Toggles.EnemyColor
  LowerTorsoRightUpper.Color = Settings.Toggles.EnemyColor
  RightLowerRightUpper.Color = Settings.Toggles.EnemyColor
  bottomrightone.Color = Settings.Toggles.EnemyColor
  bottomleftone.Color = Settings.Toggles.EnemyColor
  toprightone.Color = Settings.Toggles.EnemyColor
  topleftone.Color = Settings.Toggles.EnemyColor
  toplefttwo.Color = Settings.Toggles.EnemyColor
  bottomlefttwo.Color = Settings.Toggles.EnemyColor
  toprighttwo.Color = Settings.Toggles.EnemyColor
  bottomrighttwo.Color = Settings.Toggles.EnemyColor
end
if Funcs:IsAlive(player) and player.Character:FindFirstChild("HumanoidRootPart") then
  local RootPosition, OnScreen = Services.Camera:WorldToViewportPoint(player.Character.HumanoidRootPart.Position)
  local HeadPosition = Services.Camera:WorldToViewportPoint(player.Character.Head.Position + Vector3.new(0, 0, 0)) -- can creat an offset if u want
  local LegPosition = Services.Camera:WorldToViewportPoint(player.Character.HumanoidRootPart.Position - Vector3.new(0, 5, 0))
  local length = RootPosition.Y - ((HeadPosition.Y - LegPosition.Y) / 2)
  local lengthx = RootPosition.X - ((HeadPosition.Y - LegPosition.Y) / 2)
  local size = HeadPosition.Y - LegPosition.Y
  if Settings.Toggles.BoxEsp then
    Box.Visible = OnScreen
    Box.Size = Vector2.new(HeadPosition.Y - LegPosition.Y, HeadPosition.Y - LegPosition.Y)
    Box.Position = Vector2.new(RootPosition.X - ((HeadPosition.Y - LegPosition.Y) / 2), RootPosition.Y - ((HeadPosition.Y - LegPosition.Y) / 2))
  else
    Box.Visible = false
  end
else
  Box.Visible = false
end
end)
end

for i, v in pairs(game.Players:GetPlayers()) do
if v ~= Services.LocalPlayer then
Funcs:AddEsp(v)
end
end

game.Players.PlayerAdded:Connect(function(player)
if v ~= game.Players.LocalPlayer then
Funcs:AddEsp(player)
end
end)



local Toggle3 = Section3:CreateToggle("UI Toggle", nil, function(State)
	Window:Toggle(State)
end)
Toggle3:CreateKeybind(tostring(Config.Keybind):gsub("Enum.KeyCode.", ""), function(Key)
	Config.Keybind = Enum.KeyCode[Key]
end)

Toggle3:SetState(true)
Credits:CreateLabel("Credits Teax For The Esp Lib")
Credits:CreateLabel("Credits AlexR32#3232 For The Ui")

local Colorpicker3 = Section3:CreateColorpicker("UI Color", function(Color)
	Window:ChangeColor(Color)
end)
Colorpicker3:UpdateColor(Config.Color)
-- credits to jan for patterns
local Dropdown3 = Section4:CreateDropdown("Image")
local Option7 = Dropdown3:AddOption("Default", function(String)
	Window:SetBackground("2151741365")
end)
Dropdown3:AddOption("Hearts", function(String)
	Window:SetBackground("6073763717")
end)
Dropdown3:AddOption("Abstract", function(String)
	Window:SetBackground("6073743871")
end)
Dropdown3:AddOption("Hexagon", function(String)
	Window:SetBackground("6073628839")
end)
Dropdown3:AddOption("Circles", function(String)
	Window:SetBackground("6071579801")
end)
Dropdown3:AddOption("Lace With Flowers", function(String)
	Window:SetBackground("6071575925")
end)
Dropdown3:AddOption("Floral", function(String)
	Window:SetBackground("5553946656")
end)
Option7:SetOption()

local Colorpicker4 = Section4:CreateColorpicker("Color", function(Color)
	Window:SetBackgroundColor(Color)
end)
Colorpicker4:UpdateColor(Color3.new(1,1,1))

local Slider3 = Section4:CreateSlider("Transparency",0,1,nil,false, function(Value)
	Window:SetBackgroundTransparency(Value)
end)
Slider3:SetValue(0)

local Slider4 = Section4:CreateSlider("Tile Scale",0,1,nil,false, function(Value)
	Window:SetTileScale(Value)
end)
