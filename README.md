-- Creator: Diedre

-- Credits to infinite yield, harkinian, dex creators

prefix = ";"
wait(0.3)
Commands = {
	a
	if removingmeshhats then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Accessory")) or (v:IsA("Hat")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
	if removingmeshtool then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Tool")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
end)
game:GetService('RunService').Stepped:connect(function()
	if banpl then
		lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[bplrr].Character.HumanoidRootPart.CFrame
	end
end)
game:GetService('RunService').Stepped:connect(function()
	if stopsitting then
		lplayer.Character.Humanoid.Sit = false
	end
end)

plr = lplayer 
hum = plr.Character.HumanoidRootPart
mouse = plr:GetMouse() 
mouse.KeyDown:connect(function(key) 
	if key == "e" then 
		if mouse.Target then 
			if clickgoto then
				hum.CFrame = CFrame.new(mouse.Hit.x, mouse.Hit.y + 5, mouse.Hit.z)
			elseif clickdel then
				mouse.Target:Destroy()
			end
		end 
	end
end)

game:GetService("Workspace").ChildAdded:connect(function(part)
	if gettingtools then
		if part:IsA("Tool") then
			part.Handle.CFrame = lplayer.Character.HumanoidRootPart.CFrame
		end
	end
end)

lplayer.Chatted:Connect(function(msg)
	if string.sub(msg, 1, 6) == (prefix.."kill ") then
		if string.sub(msg, 7) == "me" then
			lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(100000,0,100000)
		else
			for i,v in pairs(GetPlayer(string.sub(msg, 7)))do
				local NOW = lplayer.Character.HumanoidRootPart.CFrame
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				local function tp(player,player2)
				local char1,char2=player.Character,player2.Character
				if char1 and char2 then
				char1:MoveTo(char2.Head.Position)
				end
				end
				wait(0.1)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.2)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.5)
				lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-100000,10,-100000))
				wait(0.7)
				tp(lplayer,game:GetService("Players")[v.Name])
				wait(0.7)
				lplayer.Character.HumanoidRootPart.CFrame = NOW
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."bring ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8)))do
			local NOW = lplayer.Character.HumanoidRootPart.CFrame
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			local function tp(player,player2)
			local char1,char2=player.Character,player2.Character
			if char1 and char2 then
			char1.HumanoidRootPart.CFrame = char2.HumanoidRootPart.CFrame
			end
			end
			local function getout(player,player2)
			local char1,char2=player.Character,player2.Character
			if char1 and char2 then
			char1:MoveTo(char2.Head.Position)
			end
			end
			tp(game:GetService("Players")[v.Name], lplayer)
			wait(0.2)
			tp(game:GetService("Players")[v.Name], lplayer)
			wait(0.5)
			lplayer.Character.HumanoidRootPart.CFrame = NOW
			wait(0.5)
			getout(lplayer, game:GetService("Players")[v.Name])
			wait(0.3)
			lplayer.Character.HumanoidRootPart.CFrame = NOW
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 6) == (prefix.."spin ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			lplayer.Character.Animate.Disabled = false
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
			spinplr = v
			wait(0.5)
			spin = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."unspin") then
		spin = false
	end
	if string.sub(msg, 1, 8) == (prefix.."attach ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
			wait(0.3)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
			attplr = v
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."unattach ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 11))) do
			local function getout(player,player2)
			local char1,char2=player.Character,player2.Character
			if char1 and char2 then
			char1:MoveTo(char2.Head.Position)
			end
			end
			getout(lplayer, game:GetService("Players")[v.Name])
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."follow ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
			followed = true
			flwplr = v
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."unfollow") then
		followed = false
	end
	if string.sub(msg, 1, 10) == (prefix.."freefall ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 11))) do
			local NOW = lplayer.Character.HumanoidRootPart.CFrame
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.2)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.6)
			lplayer.Character.HumanoidRootPart.CFrame = NOW
			wait(0.6)
			lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(0,50000,0)
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."trail ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
			traill = true
			trlplr = v
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."untrail") then
		traill = false
	end
	if string.sub(msg, 1, 7) == (prefix.."orbit ") then
		if string.sub(msg, 8) == "all" or string.sub(msg, 8) == "others" or string.sub(msg, 8) == "me" then
			lplayer.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame
		else
			for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
				local o = Instance.new("RocketPropulsion")
				o.Parent = lplayer.Character.HumanoidRootPart
				o.Name = "Orbit"
				o.Target = game:GetService("Players")[v.Name].Character.HumanoidRootPart
				o:Fire()
				noclip = true
			end
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."unorbit") then
		lplayer.Character.HumanoidRootPart.Orbit:Destroy()
		noclip = false
	end
	if string.sub(msg, 1, 7) == (prefix.."fling ") then
		if string.sub(msg, 8) == "all" or string.sub(msg, 8) == "others" or string.sub(msg, 8) == "me" then
			lplayer.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame
		else
			for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
				local y = Instance.new("RocketPropulsion")
				y.Parent = lplayer.Character.HumanoidRootPart
				y.CartoonFactor = 1
				y.MaxThrust = 800000
				y.MaxSpeed = 1000
				y.ThrustP = 200000
				y.Name = "Fling"
				game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Head
				y.Target = game:GetService("Players")[v.Name].Character.HumanoidRootPart
				y:Fire()
				noclip = true
			end
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."unfling") then
		noclip = false
		lplayer.Character.HumanoidRootPart.Fling:Destroy()
		game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Head
		wait(0.4)
		lplayer.Character.HumanoidRootPart.Fling:Destroy()
	end
	if string.sub(msg, 1, 8) == (prefix.."fecheck") then
		if game:GetService("Workspace").FilteringEnabled == true then
			warn("FE is Enabled (Filtering Enabled)")
			game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "FE is Enabled";
				Text = "Filtering Enabled. Enjoy using Reviz Admin!";
			})
		else
			warn("FE is Disabled (Filtering Disabled) Consider using a different admin script.")
			game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "FE is Disabled";
				Text = "Filtering Disabled. Consider using a different admin script.";
			})
		end
	end
	if string.sub(msg, 1, 6) == (prefix.."void ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.2)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.6)
			lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(999999999999999,0,999999999999999)
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."noclip") then
		noclip = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Noclip enabled";
		Text = "Type ;clip to disable";
		})
	end
	if string.sub(msg, 1, 5) == (prefix.."clip") then
		noclip = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Noclip disabled";
		Text = "Type ;noclip to enable";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."speed ") then
		lplayer.Character.Humanoid.WalkSpeed = (string.sub(msg, 8))
	end
	if string.sub(msg, 1, 4) == (prefix.."ws ") then
		lplayer.Character.Humanoid.WalkSpeed = (string.sub(msg, 5))
	end
	if string.sub(msg, 1, 11) == (prefix.."hipheight ") then
		lplayer.Character.Humanoid.HipHeight = (string.sub(msg, 12))
	end
	if string.sub(msg, 1, 4) == (prefix.."hh ") then
		lplayer.Character.Humanoid.HipHeight = (string.sub(msg, 5))
	end
	if string.sub(msg, 1, 11) == (prefix.."jumppower ") then
		lplayer.Character.Humanoid.JumpPower = (string.sub(msg, 12))
	end
	if string.sub(msg, 1, 4) == (prefix.."jp ") then
		lplayer.Character.Humanoid.JumpPower = (string.sub(msg, 5))
	end
	if string.sub(msg, 1, 8) == (prefix.."default") then
		lplayer.Character.Humanoid.JumpPower = 50
		lplayer.Character.Humanoid.WalkSpeed = 16
		lplayer.Character.Humanoid.HipHeight = 0
	end
	if string.sub(msg, 1, 7) == (prefix.."annoy ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
			annoying = true
			annplr = v
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."unannoy") then
		annoying = false
	end
	if string.sub(msg, 1, 10) == (prefix.."headwalk ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 11))) do
			hwalk = true
			hdwplr = v
		end
	end
	if string.sub(msg, 1, 11) == (prefix.."unheadwalk") then
		hwalk = false
	end
	if string.sub(msg, 1, 8) == (prefix.."nolimbs") then
		lplayer.Character["Left Leg"]:Destroy()
		lplayer.Character["Left Arm"]:Destroy()
		lplayer.Character["Right Leg"]:Destroy()
		lplayer.Character["Right Arm"]:Destroy()
	end
	if string.sub(msg, 1, 4) == (prefix.."god") then
		lplayer.Character.Humanoid.Name = 1
		local l = lplayer.Character["1"]:Clone()
		l.Parent = lplayer.Character
		l.Name = "Humanoid"
		wait(0.1)
		lplayer.Character["1"]:Destroy()
		game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
		lplayer.Character.Animate.Disabled = true
		wait(0.1)
		lplayer.Character.Animate.Disabled = false
		lplayer.Character.Humanoid.DisplayDistanceType = "None"
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "FE Godmode enabled";
		Text = "Use ;grespawn or ;respawn to remove";
		})
	end
	if string.sub(msg, 1, 9) == (prefix.."drophats") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Accessory")) or (v:IsA("Hat")) then
				v.Parent = workspace
			end
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."droptool") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Tool")) then
				v.Parent = workspace
			end
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."loopdhats") then
		droppinghats = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Loop Drop Enabled";
		Text = "Type ;unloopdhats to disable";
		})
	end
	if string.sub(msg, 1, 12) == (prefix.."unloopdhats") then
		droppinghats = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Loop Drop Disabled";
		Text = "Type ;loopdhats to enable.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."loopdtool") then
		droppingtools = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Loop Drop Enabled";
		Text = "Type ;unloopdtool to disable";
		})
	end
	if string.sub(msg, 1, 12) == (prefix.."unloopdtool") then
		droppingtools = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Loop Drop Disabled";
		Text = "Type ;loopdtool to enable.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."invisible") then -- Credit to Timeless
		Local = game:GetService('Players').LocalPlayer
		Char  = Local.Character
		touched,tpdback = false, false
		box = Instance.new('Part',workspace)
		box.Anchored = true
		box.CanCollide = true
		box.Size = Vector3.new(10,1,10)
		box.Position = Vector3.new(0,10000,0)
		box.Touched:connect(function(part)
		    if (part.Parent.Name == Local.Name) then
		        if touched == false then
		            touched = true
		            function apply()
		                if script.Disabled ~= true then
		                    no = Char.HumanoidRootPart:Clone()
		                    wait(.25)
		                    Char.HumanoidRootPart:Destroy()
		                    no.Parent = Char
		                    Char:MoveTo(loc)
		                    touched = false
		                end end
		            if Char then
		                apply()
		            end
		        end
		    end
		end)
		repeat wait() until Char
		loc = Char.HumanoidRootPart.Position
		Char:MoveTo(box.Position + Vector3.new(0,.5,0))
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Invisibility enabled!";
		Text = "Reset or use ;respawn to remove.";
		})
	end
	if string.sub(msg, 1, 6) == (prefix.."view ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			if game:GetService("Players")[v.Name].Character.Humanoid then
				game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Humanoid
			else
				game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Head
			end
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."unview") then
		if lplayer.Character.Humanoid then
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Humanoid
		else
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Head
		end
	end
	if string.sub(msg, 1, 6) == (prefix.."goto ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
		end
	end
	if string.sub(msg, 1, 4) == (prefix.."fly") then
	repeat wait() until lplayer and lplayer.Character and lplayer.Character:FindFirstChild('HumanoidRootPart') and lplayer.Character:FindFirstChild('Humanoid')
	repeat wait() until Mouse
	
	local T = lplayer.Character.HumanoidRootPart
	local CONTROL = {F = 0, B = 0, L = 0, R = 0}
	local lCONTROL = {F = 0, B = 0, L = 0, R = 0}
	local SPEED = speedget
	
	local function fly()
		flying = true
		local BG = Instance.new('BodyGyro', T)
		local BV = Instance.new('BodyVelocity', T)
		BG.P = 9e4
		BG.maxTorque = Vector3.new(9e9, 9e9, 9e9)
		BG.cframe = T.CFrame
		BV.velocity = Vector3.new(0, 0.1, 0)
		BV.maxForce = Vector3.new(9e9, 9e9, 9e9)
		spawn(function()
		repeat wait()
		lplayer.Character.Humanoid.PlatformStand = true
		if CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 then
		SPEED = 50
		elseif not (CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0) and SPEED ~= 0 then
		SPEED = 0
		end
		if (CONTROL.L + CONTROL.R) ~= 0 or (CONTROL.F + CONTROL.B) ~= 0 then
		BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (CONTROL.F + CONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(CONTROL.L + CONTROL.R, (CONTROL.F + CONTROL.B) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
		lCONTROL = {F = CONTROL.F, B = CONTROL.B, L = CONTROL.L, R = CONTROL.R}
		elseif (CONTROL.L + CONTROL.R) == 0 and (CONTROL.F + CONTROL.B) == 0 and SPEED ~= 0 then
		BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (lCONTROL.F + lCONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(lCONTROL.L + lCONTROL.R, (lCONTROL.F + lCONTROL.B) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
		else
		BV.velocity = Vector3.new(0, 0.1, 0)
		end
		BG.cframe = workspace.CurrentCamera.CoordinateFrame
				until not flying
				CONTROL = {F = 0, B = 0, L = 0, R = 0}
				lCONTROL = {F = 0, B = 0, L = 0, R = 0}
				SPEED = 0
				BG:destroy()
				BV:destroy()
				lplayer.Character.Humanoid.PlatformStand = false
			end)
		end
	Mouse.KeyDown:connect(function(KEY)
		if KEY:lower() == 'w' then
			CONTROL.F = speedfly
		elseif KEY:lower() == 's' then
			CONTROL.B = -speedfly
		elseif KEY:lower() == 'a' then
			CONTROL.L = -speedfly 
		elseif KEY:lower() == 'd' then 
			CONTROL.R = speedfly
		end
	end)
	Mouse.KeyUp:connect(function(KEY)
		if KEY:lower() == 'w' then
			CONTROL.F = 0
		elseif KEY:lower() == 's' then
			CONTROL.B = 0
		elseif KEY:lower() == 'a' then
			CONTROL.L = 0
		elseif KEY:lower() == 'd' then
			CONTROL.R = 0
		end
	end)
	fly()
	end
	if string.sub(msg, 1, 6) == (prefix.."unfly") then
		flying = false
		lplayer.Character.Humanoid.PlatformStand = false
	end
	if string.sub(msg, 1, 6) == (prefix.."chat ") then
		game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer((string.sub(msg, 7)), "All")
	end
	if string.sub(msg, 1, 6) == (prefix.."spam ") then
		spamtext = (string.sub(msg, 7))
		spamming = true
	end
	if string.sub(msg, 1, 7) == (prefix.."unspam") then
		spamming = false
	end
	if string.sub(msg, 1, 10) == (prefix.."spamwait ") then
		spamdelay = (string.sub(msg, 11))
	end
	if string.sub(msg, 1, 8) == (prefix.."pmspam ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
			pmspammed = v.Name
			spammingpm = true
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."unpmspam") then
		spammingpm = false
	end
	if string.sub(msg, 1, 9) == (prefix.."cfreeze ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 10))) do
			v.Character["Left Leg"].Anchored = true
			v.Character["Left Arm"].Anchored = true
			v.Character["Right Leg"].Anchored = true
			v.Character["Right Arm"].Anchored = true
			v.Character.Torso.Anchored = true
			v.Character.Head.Anchored = true
		end
	end
	if string.sub(msg, 1, 11) == (prefix.."uncfreeze ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 12))) do
			v.Character["Left Leg"].Anchored = false
			v.Character["Left Arm"].Anchored = false
			v.Character["Right Leg"].Anchored = false
			v.Character["Right Arm"].Anchored = false
			v.Character.Torso.Anchored = false
			v.Character.Head.Anchored = false
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."unlockws") then
		local a = game:GetService("Workspace"):getChildren()
		for i = 1, #a do
			if a[i].className == "Part" then
				a[i].Locked = false
			elseif a[i].className == "Model" then
				local r = a[i]:getChildren()
				for i = 1, #r do
					if r[i].className == "Part" then
					r[i].Locked = false
					end
				end
			end
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Success!";
		Text = "Workspace unlocked. Use ;lockws to lock.";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."lockws") then
		local a = game:GetService("Workspace"):getChildren()
		for i = 1, #a do
			if a[i].className == "Part" then
				a[i].Locked = true
			elseif a[i].className == "Model" then
				local r = a[i]:getChildren()
				for i = 1, #r do
					if r[i].className == "Part" then
					r[i].Locked = true
					end
				end
			end
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."btools") then
		local Clone_T = Instance.new("HopperBin",lplayer.Backpack)
		Clone_T.BinType = "Clone"
		local Destruct = Instance.new("HopperBin",lplayer.Backpack)
		Destruct.BinType = "Hammer"
		local Hold_T = Instance.new("HopperBin",lplayer.Backpack)
		Hold_T.BinType = "Grab"
	end
	if string.sub(msg, 1, 7) == (prefix.."pstand") then
		lplayer.Character.Humanoid.PlatformStand = true
	end
	if string.sub(msg, 1, 9) == (prefix.."unpstand") then
		lplayer.Character.Humanoid.PlatformStand = false
	end
	if string.sub(msg, 1, 10) == (prefix.."blockhead") then
		lplayer.Character.Head.Mesh:Destroy()
	end
	if string.sub(msg, 1, 4) == (prefix.."sit") then
		lplayer.Character.Humanoid.Sit = true
	end
	if string.sub(msg, 1, 10) == (prefix.."bringobj ") then
		local function bringobjw()
		for i,obj in ipairs(game:GetService("Workspace"):GetDescendants()) do
		if obj.Name == (string.sub(msg, 11)) then
		obj.CFrame = lplayer.Character.HumanoidRootPart.CFrame
		obj.CanCollide = false
		obj.Transparency = 0.7
		wait()
		obj.CFrame = lplayer.Character["Left Leg"].CFrame
		wait()
		obj.CFrame = lplayer.Character["Right Leg"].CFrame
		wait()
		obj.CFrame = lplayer.Character["Head"].CFrame
		end
		end
		end
		while wait() do
			bringobjw()
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "BringObj";
		Text = "BringObj enabled.";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."wsvis ") then
		vis = (string.sub(msg, 8))
		local a = game:GetService("Workspace"):GetDescendants()
		for i = 1, #a do
			if a[i].className == "Part" then
				a[i].Transparency = vis
			elseif a[i].className == "Model" then
				local r = a[i]:getChildren()
				for i = 1, #r do
					if r[i].className == "Part" then
					r[i].Transparency = vis
					end
				end
			end
		end
	end
	if string.sub(msg, 1, 11) == (prefix.."hypertotal") then
		loadstring(game:GetObjects("rbxassetid://1255063809")[1].Source)()
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Success!";
		Text = "HyperTotal GUI Loaded!";
		})
	end
	if string.sub(msg, 1, 5) == (prefix.."cmds") then
		CMDSFRAME.Visible = true
	end
	if string.sub(msg, 1, 10) == (prefix.."rmeshhats") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Accessory")) or (v:IsA("Hat")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."blockhats") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Accessory")) or (v:IsA("Hat")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."rmeshtool") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Tool")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."blocktool") then
		for i,v in pairs(lplayer.Character:GetChildren()) do
			if (v:IsA("Tool")) then
				v.Handle.Mesh:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."spinner") then
		local p = Instance.new("RocketPropulsion")
		p.Parent = lplayer.Character.HumanoidRootPart
		p.Name = "Spinner"
		p.Target = lplayer.Character["Left Arm"]
		p:Fire()
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Spinner enabled";
		Text = "Type ;nospinner to disable.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."nospinner") then
		lplayer.Character.HumanoidRootPart.Spinner:Destroy()
	end
	if string.sub(msg, 1, 7) == (prefix.."reachd") then
		for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
			if v:isA("Tool") then
				local a = Instance.new("SelectionBox",v.Handle)
				a.Adornee = v.Handle
				v.Handle.Size = Vector3.new(0.5,0.5,60)
				v.GripPos = Vector3.new(0,0,0)
				lplayer.Character.Humanoid:UnequipTools()
			end
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Reach applied!";
		Text = "Applied to equipped sword. Use ;noreach to disable.";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."reach ") then
		for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
			if v:isA("Tool") then
				handleSize = v.Handle.Size
				wait()
				local a = Instance.new("SelectionBox",v.Handle)
				a.Name = "a"
				a.Adornee = v.Handle
				v.Handle.Size = Vector3.new(0.5,0.5,(string.sub(msg, 8)))
				v.GripPos = Vector3.new(0,0,0)
				lplayer.Character.Humanoid:UnequipTools()
			end
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Reach applied!";
		Text = "Applied to equipped sword. Use ;noreach to disable.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."noreach") then
		for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
			if v:isA("Tool") then
				v.Handle.a:Destroy()
				v.Handle.Size = handleSize
			end
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Reach removed!";
		Text = "Removed reach from equipped sword.";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."rkill ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8)))do
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			wait(0.1)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.2)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.5)
			lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-100000,10,-100000))
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."tp me ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."cbring ") then
		if (string.sub(msg, 9)) == "all" or (string.sub(msg, 9)) == "All" or (string.sub(msg, 9)) == "ALL" then
			cbringall = true
		else
			for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
				brplr = v.Name
			end
		end
		cbring = true
	end
	if string.sub(msg, 1, 9) == (prefix.."uncbring") then
		cbring = false
		cbringall = false
	end
	if string.sub(msg, 1, 6) == (prefix.."swap ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			local NOWPLR = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			local NOW = lplayer.Character.HumanoidRootPart.CFrame
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			local function tp(player,player2)
			local char1,char2=player.Character,player2.Character
			if char1 and char2 then
			char1:MoveTo(char2.Head.Position)
			end
			end
			wait(0.1)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.2)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			wait(0.5)
			lplayer.Character.HumanoidRootPart.CFrame = NOW
			wait(0.6)
			tp(lplayer, game:GetService("Players")[v.Name])
			wait(0.4)
			lplayer.Character.HumanoidRootPart.CFrame = NOWPLR
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."glitch ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
			lplayer.Character.Humanoid:EquipTool(v)
			end
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
			wait(0.3)
			lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
			wait(0.4)
			b = Instance.new("BodyForce")
			b.Parent = lplayer.Character.HumanoidRootPart
			b.Name = "Glitch"
			b.Force = Vector3.new(100000000,5000,0)
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools needed!";
			Text = "You need a tool in your backpack for this command!";
			})
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."unglitch") then
		lplayer.Character.HumanoidRootPart.Glitch:Destroy()
		lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(10000,0,10000)
		b = Instance.new("BodyForce")
		b.Parent = lplayer.Character.HumanoidRootPart
		b.Name = "unGlitch"
		b.Force = Vector3.new(0,-5000000,0)
		wait(2)
		lplayer.Character.HumanoidRootPart.unGlitch:Destroy()
	end
	if string.sub(msg, 1, 9) == (prefix.."grespawn") then
		lplayer.Character.Humanoid.Health = 0
		wait(1)
		lplayer.Character.Head.CFrame = CFrame.new(1000000,0,1000000)
		lplayer.Character.Torso.CFrame = CFrame.new(1000000,0,1000000)
	end
	if string.sub(msg, 1, 9) == (prefix.."explorer") then
		loadstring(game:GetObjects("rbxassetid://492005721")[1].Source)()
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Success!";
		Text = "DEX Explorer has loaded.";
		})
	end
	if string.sub(msg, 1, 6) == (prefix.."anim ") then
		local Anim = Instance.new("Animation")
		Anim.AnimationId = "rbxassetid://"..(string.sub(msg, 7))
		local track = lplayer.Character.Humanoid:LoadAnimation(Anim)
		track:Play(.1, 1, 1)
	end
	if string.sub(msg, 1, 8) == (prefix.."animgui") then
		loadstring(game:GetObjects("rbxassetid://1202558084")[1].Source)()
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Success!";
		Text = "Energize Animations GUI has loaded.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."savepos") then
		saved = lplayer.Character.HumanoidRootPart.CFrame
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Position Saved";
		Text = "Use ;loadpos to return to saved position.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."loadpos") then
		lplayer.Character.HumanoidRootPart.CFrame = saved
	end
	if string.sub(msg, 1, 6) == (prefix.."bang ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 7))) do
			local Anim2 = Instance.new("Animation")
			Anim2.AnimationId = "rbxassetid://148840371"
			local track2 = lplayer.Character.Humanoid:LoadAnimation(Anim2)
			track2:Play(.1, 1, 1)
			bplrr = v.Name
			banpl = true
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."unbang") then
		banpl = false
	end
	if string.sub(msg, 1, 10) == (prefix.."bringmod ") then
		local function bringmodw()
		for i,obj in ipairs(game:GetService("Workspace"):GetDescendants()) do
		if obj.Name == (string.sub(msg, 11)) then
		for i,ch in pairs(obj:GetDescendants()) do
		if (ch:IsA("BasePart")) then
		ch.CFrame = lplayer.Character.HumanoidRootPart.CFrame
		ch.CanCollide = false
		ch.Transparency = 0.7
		wait()
		ch.CFrame = lplayer.Character["Left Leg"].CFrame
		wait()
		ch.CFrame = lplayer.Character["Right Leg"].CFrame
		wait()
		ch.CFrame = lplayer.Character["Head"].CFrame
		end
		end
		end
		end
		end
		while wait() do
			bringmodw()
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "BringMod";
		Text = "BringMod enabled.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."respawn") then
		local mod = Instance.new('Model', workspace) mod.Name = 're '..lplayer.Name
		local hum = Instance.new('Humanoid', mod)
		local ins = Instance.new('Part', mod) ins.Name = 'Torso' ins.CanCollide = false ins.Transparency = 1
		lplayer.Character = mod
	end
	if string.sub(msg, 1, 9) == (prefix.."shutdown") then
		game:GetService'RunService'.Stepped:Connect(function()
		pcall(function()
		    for i,v in pairs(game:GetService'Players':GetPlayers()) do
		        if v.Character ~= nil and v.Character:FindFirstChild'Head' then
		            for _,x in pairs(v.Character.Head:GetChildren()) do
		                if x:IsA'Sound' then x.Playing = true x.CharacterSoundEvent:FireServer(true, true) end
		            end
		        end
		    end
		end)
		end)
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Attempting Shutdown";
		Text = "Shutdown Attempt has begun.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."delobj ") then
		objtodel = (string.sub(msg, 9))
		for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
			if v.Name == objtodel then
				v:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."getplrs") then
		for i,v in pairs(game:GetService("Players"):GetPlayers())do
			print(v)
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Printed";
		Text = "Players have been printed to console. (F9)";
		})
	end
	if string.sub(msg, 1, 9) == (prefix.."deldecal") then
		for i,v in pairs(game:GetService("Workspace"):GetDescendants())do
			if (v:IsA("Decal")) then
				v:Destroy()
			end
		end
	end
	if string.sub(msg, 1, 11) == (prefix.."opfinality") then
		loadstring(game:GetObjects("rbxassetid://1294358929")[1].Source)()
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Success!";
		Text = "OpFinality GUI has loaded.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."remotes") then
		remotes = true
		added = true
		game.DescendantAdded:connect(function(rmt)
		if added == true then
		if remotes == true then 
		if rmt:IsA("RemoteEvent") then
		print("A RemoteEvent was added!")
		print(" game." .. rmt:GetFullName() .. " | RemoteEvent")
		print(" game." .. rmt:GetFullName() .. " | RemoteEvent", 247, 0, 0, true)
		end end end
		end)
		game.DescendantAdded:connect(function(rmtfnctn)
		if added == true then
		if remotes == true then 
		if rmtfnctn:IsA("RemoteFunction") then
		warn("A RemoteFunction was added!")
		warn(" game." .. rmtfnctn:GetFullName() .. " | RemoteFunction")
		print(" game." .. rmtfnctn:GetFullName() .. " | RemoteFunction", 5, 102, 198, true)
		end end end
		end)
		
		game.DescendantAdded:connect(function(bndfnctn)
		if added == true then
		if binds == true then 
		if bndfnctn:IsA("BindableFunction") then
		print("A BindableFunction was added!")
		print(" game." .. bndfnctn:GetFullName() .. " | BindableFunction")
		print(" game." .. bndfnctn:GetFullName() .. " | BindableFunction", 239, 247, 4, true)
		end end end
		end)
		
		game.DescendantAdded:connect(function(bnd)
		if added == true then
		if binds == true then 
		if bnd:IsA("BindableEvent") then
		warn("A BindableEvent was added!")
		warn(" game." .. bnd:GetFullName() .. " | BindableEvent")
		print(" game." .. bnd:GetFullName() .. " | BindableEvent", 13, 193, 22, true)
		end end end
		end)
		
		
		if binds == true then
		for i,v in pairs(game:GetDescendants()) do
		if v:IsA("BindableFunction") then
		print(" game." .. v:GetFullName() .. " | BindableFunction")
		print(" game." .. v:GetFullName() .. " | BindableFunction", 239, 247, 4, true)
		end end
		for i,v in pairs(game:GetDescendants()) do
		if v:IsA("BindableEvent") then
		warn(" game." .. v:GetFullName() .. " | BindableEvent")
		print(" game." .. v:GetFullName() .. " | BindableEvent", 13, 193, 22, true)
		end end
		else
		print("Off")
		end
		if remotes == true then
		for i,v in pairs(game:GetDescendants()) do
		if v:IsA("RemoteFunction") then
		warn(" game." .. v:GetFullName() .. " | RemoteFunction")
		print(" game." .. v:GetFullName() .. " | RemoteFunction", 5, 102, 198, true)
		end end
		wait()
		for i,v in pairs(game:GetDescendants()) do
		if v:IsA("RemoteEvent") then
		print(" game." .. v:GetFullName() .. " | RemoteEvent")
		print(" game." .. v:GetFullName() .. " | RemoteEvent", 247, 0, 0, true)
		end end
		else
		print("Off")
		end
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Printing Remotes";
		Text = "Type ;noremotes to disable.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."noremotes") then
		remotes = false
		added = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Printing Remotes Disabled";
		Text = "Type ;remotes to enable.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."tpdefault") then
		spin = false
		followed = false
		traill = false
		noclip = false
		annoying = false
		hwalk = false
		cbringing = false
	end
	if string.sub(msg, 1, 8) == (prefix.."stopsit") then
		stopsitting = true
	end
	if string.sub(msg, 1, 6) == (prefix.."gosit") then
		stopsitting = false
	end
	if string.sub(msg, 1, 8) == (prefix.."version") then
		print(adminversion)
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Version";
		Text = adminversion;
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."clicktp") then
		clickgoto = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Click TP";
		Text = "Press E to teleport to mouse position, ;noclicktp to stop";
		})
	end
	if string.sub(msg, 1, 9) == (prefix.."clickdel") then
		clickdel = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Click Delete";
		Text = "Press E to delete part at mouse, ;noclickdel to stop";
		})
	end
	if string.sub(msg, 1, 11) == (prefix.."noclickdel") then
		clickdel = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Click Delete";
		Text = "Click delete has been disabled.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."noclicktp") then
		clickgoto = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Click TP";
		Text = "Click TP has been disabled.";
		})
	end
	if string.sub(msg, 1, 8) == (prefix.."toolson") then
		gettingtools = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Tools Enabled";
		Text = "Automatically colleting tools dropped.";
		})
	end
	if string.sub(msg, 1, 9) == (prefix.."toolsoff") then
		gettingtools = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Tools Disabled";
		Text = "Click TP has been disabled.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."delcmdbar") then
		ScreenGui:Destroy()
	end
	if string.sub(msg, 1, 6) == (prefix.."reset") then
		lplayer.Character.Head:Destroy()
	end
	if string.sub(msg, 1, 7) == (prefix.."state ") then
		statechosen = string.sub(msg, 8)
		changingstate = true
	end
	if string.sub(msg, 1, 9) == (prefix.."gravity ") then
		game:GetService("Workspace").Gravity = string.sub(msg, 10)
	end
	if string.sub(msg, 1, 10) == (prefix.."looprhats") then
		removingmeshhats = true
	end
	if string.sub(msg, 1, 12) == (prefix.."unlooprhats") then
		removingmeshhats = false
	end
	if string.sub(msg, 1, 10) == (prefix.."looprtool") then
		removingmeshtool = true
	end
	if string.sub(msg, 1, 12) == (prefix.."unlooprtool") then
		removingmeshtool = false
	end
	if string.sub(msg, 1, 10) == (prefix.."givetool ") then
		for i,v in pairs(game:GetService("Players").LocalPlayer.Character:GetDescendants()) do
			if v:IsA("Tool") then
				for i,player in pairs(GetPlayer(string.sub(msg, 11))) do
					v.Parent = player.Character
				end
			end
		end
	end
	if string.sub(msg, 1, 14) == (prefix.."givealltools ") then
		for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetDescendants()) do
			if v:IsA("Tool") then
				v.Parent = lplayer.Character
				wait()
				for i,player in pairs(GetPlayer(string.sub(msg, 15))) do
					v.Parent = player.Character
				end
			end
		end
	end
	if string.sub(msg, 1, 5) == (prefix.."age ") then
		for i,player in pairs(GetPlayer(string.sub(msg, 6))) do
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(player.Name.." Account Age: "..player.AccountAge.." days!", "All")
		end
	end
	if string.sub(msg, 1, 4) == (prefix.."id ") then
		for i,player in pairs(GetPlayer(string.sub(msg, 5))) do
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(player.Name.." Account ID: "..player.UserId, "All")
		end
	end
	if string.sub(msg, 1, 6) == (prefix..".age ") then
		for i,player in pairs(GetPlayer(string.sub(msg, 7))) do
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = player.AccountAge.." Days";
			Text = "Account age of "..player.Name;
			})
		end
	end
	if string.sub(msg, 1, 5) == (prefix..".id ") then
		for i,player in pairs(GetPlayer(string.sub(msg, 6))) do
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = player.UserId.." ID";
			Text = "Account ID of "..player.Name;
			})
		end
	end
	if string.sub(msg, 1, 7) == (prefix.."gameid") then
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Game ID";
		Text = "Game ID: ".. game.GameId;
		})
	end
	if string.sub(msg, 1, 4) == (prefix.."pgs") then
		local pgscheck = game:GetService("Workspace"):PGSIsEnabled()
		if pgscheck == true then
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "PGSPhysicsSolverEnabled";
			Text = "PGS is Enabled!";
			})
		else
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "PGSPhysicsSolverEnabled";
			Text = "PGS is Disabled!";
			})
		end
	end
	if string.sub(msg, 1, 12) == (prefix.."removeinvis") then
		for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
			if v:IsA("Part") then
				if v.Transparency == 1 then
					if v.Name ~= "HumanoidRootPart" then
						v:Destroy()
					end
				end
			end
		end
	end
	if string.sub(msg, 1, 10) == (prefix.."removefog") then
		game:GetService("Lighting").FogStart = 0
		game:GetService("Lighting").FogEnd = 9999999999999
	end
	if string.sub(msg, 1, 8) == (prefix.."disable") then
		lplayer.Character.Humanoid.Parent = lplayer
	end
	if string.sub(msg, 1, 7) == (prefix.."enable") then
		lplayer.Humanoid.Parent = lplayer.Character
	end
	if string.sub(msg, 1, 8) == (prefix.."prefix ") then
		prefix = (string.sub(msg, 9, 9))
		wait(0.1)
		change()
		wait(0.1)
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Prefix changed!";
		Text = "Prefix is now "..prefix..". Use ;resetprefix to reset to ;";
		})
	end
	if string.sub(msg, 1, 12) == (";resetprefix") then
		prefix = ";"
		wait(0.1)
		change()
		wait(0.1)
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "Prefix changed!";
		Text = "Prefix is now "..prefix..". Make sure it's one key!";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."flyspeed ") then
		speedfly = string.sub(msg, 11)
		wait()
		change()
	end
	if string.sub(msg, 1, 8) == (prefix.."carpet ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 9))) do
			local Anim3 = Instance.new("Animation")
			Anim3.AnimationId = "rbxassetid://282574440"
			local track3 = lplayer.Character.Humanoid:LoadAnimation(Anim3)
			track3:Play(.1, 1, 1)
			bplrr = v.Name
			banpl = true
		end
	end
	if string.sub(msg, 1, 9) == (prefix.."uncarpet") then
		banpl = false
	end
	if string.sub(msg, 1, 7) == (prefix.."stare ") then
		for i,v in pairs(GetPlayer(string.sub(msg, 8))) do
			staring = true
			stareplr = v
		end
	end
	if string.sub(msg, 1, 8) == (prefix.."unstare") then
		staring = false
	end
	if string.sub(msg, 1, 8) == (prefix.."logchat") then
		chatlogs = true
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "LogChat enabled";
		Text = "Now logging all player chat.";
		})
	end
	if string.sub(msg, 1, 10) == (prefix.."unlogchat") then
		chatlogs = false
		game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "LogChat disabled";
		Text = "Stopped logging all player chat.";
		})
	end
	if string.sub(msg, 1, 7) == (prefix.."fixcam") then
		game:GetService("Workspace").CurrentCamera:Destroy()
		wait(0.1)
		game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Humanoid
		game:GetService("Workspace").CurrentCamera.CameraType = "Custom"
		lplayer.CameraMinZoomDistance = 0.5
		lplayer.CameraMaxZoomDistance = 400
		lplayer.CameraMode = "Classic"
	end
	if string.sub(msg, 1, 8) == (prefix.."unstate") then
		changingstate = false
	end
end)

local function tp()
	for i, player in ipairs(game:GetService("Players"):GetPlayers()) do
		if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
			if player.Name == brplr then
				player.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame + lplayer.Character.HumanoidRootPart.CFrame.lookVector * 2
			end
		end
	end
end
local function tpall()
	for i, player in ipairs(game:GetService("Players"):GetPlayers()) do
		if player.Character and player.Character:FindFirstChild("HumanoidRootPart") then
			player.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame + lplayer.Character.HumanoidRootPart.CFrame.lookVector * 3
		end
	end
end
spawn(function()
	while wait(spamdelay) do
		if spamming == true then
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(spamtext, "All")
		end
	end
end)
spawn(function()
	while wait(spamdelay) do
		if spammingpm == true then
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer("/w "..pmspammed.." @@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@@", "All")
		end
	end
end)
spawn(function()
	while wait() do
		if cbring == true then
			tp()
		end
	end
end)
spawn(function()
	while wait() do
		if cbringall == true then
			tpall()
		end
	end
end)

Mouse.KeyDown:connect(function(Key)
	if Key == prefix then
		CMDBAR:CaptureFocus()
	end
end)

CMDBAR.FocusLost:connect(function(enterPressed)
	if enterPressed then
		if string.sub(CMDBAR.Text, 1, 5) == ("kill ") then
			if string.sub(CMDBAR.Text, 6) == "me" then
				lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(100000,0,100000)
			else
				for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6)))do
					local NOW = lplayer.Character.HumanoidRootPart.CFrame
					lplayer.Character.Humanoid.Name = 1
					local l = lplayer.Character["1"]:Clone()
					l.Parent = lplayer.Character
					l.Name = "Humanoid"
					wait(0.1)
					lplayer.Character["1"]:Destroy()
					game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
					lplayer.Character.Animate.Disabled = true
					wait(0.1)
					lplayer.Character.Animate.Disabled = false
					lplayer.Character.Humanoid.DisplayDistanceType = "None"
					for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
					lplayer.Character.Humanoid:EquipTool(v)
					end
					local function tp(player,player2)
					local char1,char2=player.Character,player2.Character
					if char1 and char2 then
					char1:MoveTo(char2.Head.Position)
					end
					end
					wait(0.1)
					lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
					wait(0.2)
					lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
					wait(0.5)
					lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-100000,10,-100000))
					wait(0.7)
					tp(lplayer,game:GetService("Players")[v.Name])
					wait(0.7)
					lplayer.Character.HumanoidRootPart.CFrame = NOW
					game:GetService("StarterGui"):SetCore("SendNotification", {
					Title = "Tools needed!";
					Text = "You need a tool in your backpack for this command!";
					})
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("bring ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7)))do
				local NOW = lplayer.Character.HumanoidRootPart.CFrame
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				local function tp(player,player2)
				local char1,char2=player.Character,player2.Character
				if char1 and char2 then
				char1.HumanoidRootPart.CFrame = char2.HumanoidRootPart.CFrame
				end
				end
				local function getout(player,player2)
				local char1,char2=player.Character,player2.Character
				if char1 and char2 then
				char1:MoveTo(char2.Head.Position)
				end
				end
				tp(game:GetService("Players")[v.Name], lplayer)
				wait(0.2)
				tp(game:GetService("Players")[v.Name], lplayer)
				wait(0.5)
				lplayer.Character.HumanoidRootPart.CFrame = NOW
				wait(0.5)
				getout(lplayer, game:GetService("Players")[v.Name])
				wait(0.3)
				lplayer.Character.HumanoidRootPart.CFrame = NOW
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("spin ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
				spinplr = v
				wait(0.5)
				spin = true
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("unspin") then
			spin = false
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("attach ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
				wait(0.3)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
				attplr = v
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("unattach ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 10))) do
				local function getout(player,player2)
				local char1,char2=player.Character,player2.Character
				if char1 and char2 then
				char1:MoveTo(char2.Head.Position)
				end
				end
				getout(lplayer, game:GetService("Players")[v.Name])
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("follow ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
				followed = true
				flwplr = v
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("unfollow") then
			followed = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("freefall ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 10))) do
				local NOW = lplayer.Character.HumanoidRootPart.CFrame
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.2)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.6)
				lplayer.Character.HumanoidRootPart.CFrame = NOW
				wait(0.6)
				lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(0,50000,0)
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("trail ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
				traill = true
				trlplr = v
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("untrail") then
			traill = false
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("orbit ") then
			if string.sub(CMDBAR.Text, 7) == "all" or string.sub(CMDBAR.Text, 7) == "others" or string.sub(CMDBAR.Text, 7) == "me" then
				lplayer.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame
			else
				for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
					local o = Instance.new("RocketPropulsion")
					o.Parent = lplayer.Character.HumanoidRootPart
					o.Name = "Orbit"
					o.Target = game:GetService("Players")[v.Name].Character.HumanoidRootPart
					o:Fire()
					noclip = true
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("unorbit") then
			lplayer.Character.HumanoidRootPart.Orbit:Destroy()
			noclip = false
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("fling ") then
			if string.sub(CMDBAR.Text, 7) == "all" or string.sub(CMDBAR.Text, 7) == "others" or string.sub(CMDBAR.Text, 7) == "me" then
				lplayer.Character.HumanoidRootPart.CFrame = lplayer.Character.HumanoidRootPart.CFrame
			else
				for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
					local y = Instance.new("RocketPropulsion")
					y.Parent = lplayer.Character.HumanoidRootPart
					y.CartoonFactor = 1
					y.MaxThrust = 800000
					y.MaxSpeed = 1000
					y.ThrustP = 200000
					y.Name = "Fling"
					game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Head
					y.Target = game:GetService("Players")[v.Name].Character.HumanoidRootPart
					y:Fire()
					noclip = true
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("unfling") then
			noclip = false
			lplayer.Character.HumanoidRootPart.Fling:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Head
			wait(0.4)
			lplayer.Character.HumanoidRootPart.Fling:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("fecheck") then
			if game:GetService("Workspace").FilteringEnabled == true then
				warn("FE is Enabled (Filtering Enabled)")
				game:GetService("StarterGui"):SetCore("SendNotification", {
					Title = "FE is Enabled";
					Text = "Filtering Enabled. Enjoy using Reviz Admin!";
				})
			else
				warn("FE is Disabled (Filtering Disabled) Consider using a different admin script.")
				game:GetService("StarterGui"):SetCore("SendNotification", {
					Title = "FE is Disabled";
					Text = "Filtering Disabled. Consider using a different admin script.";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("void ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.2)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.6)
				lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(999999999999999,0,999999999999999)
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("noclip") then
			noclip = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Noclip enabled";
			Text = "Type ;clip to disable";
			})
		end
		if string.sub(CMDBAR.Text, 1, 4) == ("clip") then
			noclip = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Noclip disabled";
			Text = "Type ;noclip to enable";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("speed ") then
			lplayer.Character.Humanoid.WalkSpeed = (string.sub(CMDBAR.Text, 7))
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("ws ") then
			lplayer.Character.Humanoid.WalkSpeed = (string.sub(CMDBAR.Text, 4))
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("hipheight ") then
			lplayer.Character.Humanoid.HipHeight = (string.sub(CMDBAR.Text, 11))
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("hh ") then
			lplayer.Character.Humanoid.HipHeight = (string.sub(CMDBAR.Text, 4))
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("jumppower ") then
			lplayer.Character.Humanoid.JumpPower = (string.sub(CMDBAR.Text, 11))
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("jp ") then
			lplayer.Character.Humanoid.JumpPower = (string.sub(CMDBAR.Text, 4))
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("default") then
			lplayer.Character.Humanoid.JumpPower = 50
			lplayer.Character.Humanoid.WalkSpeed = 16
			lplayer.Character.Humanoid.HipHeight = 0
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("annoy ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
				annoying = true
				annplr = v
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("unannoy") then
			annoying = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("headwalk ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 10))) do
				hwalk = true
				hdwplr = v
			end
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("unheadwalk") then
			hwalk = false
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("nolimbs") then
			lplayer.Character["Left Leg"]:Destroy()
			lplayer.Character["Left Arm"]:Destroy()
			lplayer.Character["Right Leg"]:Destroy()
			lplayer.Character["Right Arm"]:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("god") then
			lplayer.Character.Humanoid.Name = 1
			local l = lplayer.Character["1"]:Clone()
			l.Parent = lplayer.Character
			l.Name = "Humanoid"
			wait(0.1)
			lplayer.Character["1"]:Destroy()
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
			lplayer.Character.Animate.Disabled = true
			wait(0.1)
			lplayer.Character.Animate.Disabled = false
			lplayer.Character.Humanoid.DisplayDistanceType = "None"
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "FE Godmode enabled";
			Text = "Use ;grespawn or ;respawn to remove.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("drophats") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Accessory")) or (v:IsA("Hat")) then
					v.Parent = workspace
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("droptool") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Tool")) then
					v.Parent = workspace
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("loopdhats") then
			droppinghats = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Loop Drop Enabled";
			Text = "Type ;unloopdhats to disable";
			})
		end
		if string.sub(CMDBAR.Text, 1, 11) == ("unloopdhats") then
			droppinghats = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Loop Drop Disabled";
			Text = "Type ;loopdhats to enable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("loopdtool") then
			droppingtools = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Loop Drop Enabled";
			Text = "Type ;unloopdtool to disable";
			})
		end
		if string.sub(CMDBAR.Text, 1, 11) == ("unloopdtool") then
			droppingtools = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Loop Drop Disabled";
			Text = "Type ;loopdtool to enable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("invisible") then -- Credit to Timeless
			Local = game:GetService('Players').LocalPlayer
			Char  = Local.Character
			touched,tpdback = false, false
			box = Instance.new('Part',workspace)
			box.Anchored = true
			box.CanCollide = true
			box.Size = Vector3.new(10,1,10)
			box.Position = Vector3.new(0,10000,0)
			box.Touched:connect(function(part)
			    if (part.Parent.Name == Local.Name) then
			        if touched == false then
			            touched = true
			            function apply()
			                if script.Disabled ~= true then
			                    no = Char.HumanoidRootPart:Clone()
			                    wait(.25)
			                    Char.HumanoidRootPart:Destroy()
			                    no.Parent = Char
			                    Char:MoveTo(loc)
			                    touched = false
			                end end
			            if Char then
			                apply()
			            end
			        end
			    end
			end)
			repeat wait() until Char
			loc = Char.HumanoidRootPart.Position
			Char:MoveTo(box.Position + Vector3.new(0,.5,0))
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Invisibility enabled!";
			Text = "Reset or use ;respawn to remove.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("view ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				if game:GetService("Players")[v.Name].Character.Humanoid then
					game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Humanoid
				else
					game:GetService("Workspace").CurrentCamera.CameraSubject = game:GetService("Players")[v.Name].Character.Head
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("unview") then
			if lplayer.Character.Humanoid then
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Humanoid
			else
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Head
			end
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("goto ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			end
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("fly") then
		repeat wait() until lplayer and lplayer.Character and lplayer.Character:FindFirstChild('HumanoidRootPart') and lplayer.Character:FindFirstChild('Humanoid')
		repeat wait() until Mouse
		
		local T = lplayer.Character.HumanoidRootPart
		local CONTROL = {F = 0, B = 0, L = 0, R = 0}
		local lCONTROL = {F = 0, B = 0, L = 0, R = 0}
		local SPEED = speedget
		
		local function fly()
			flying = true
			local BG = Instance.new('BodyGyro', T)
			local BV = Instance.new('BodyVelocity', T)
			BG.P = 9e4
			BG.maxTorque = Vector3.new(9e9, 9e9, 9e9)
			BG.cframe = T.CFrame
			BV.velocity = Vector3.new(0, 0.1, 0)
			BV.maxForce = Vector3.new(9e9, 9e9, 9e9)
			spawn(function()
			repeat wait()
			lplayer.Character.Humanoid.PlatformStand = true
			if CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0 then
			SPEED = 50
			elseif not (CONTROL.L + CONTROL.R ~= 0 or CONTROL.F + CONTROL.B ~= 0) and SPEED ~= 0 then
			SPEED = 0
			end
			if (CONTROL.L + CONTROL.R) ~= 0 or (CONTROL.F + CONTROL.B) ~= 0 then
			BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (CONTROL.F + CONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(CONTROL.L + CONTROL.R, (CONTROL.F + CONTROL.B) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
			lCONTROL = {F = CONTROL.F, B = CONTROL.B, L = CONTROL.L, R = CONTROL.R}
			elseif (CONTROL.L + CONTROL.R) == 0 and (CONTROL.F + CONTROL.B) == 0 and SPEED ~= 0 then
			BV.velocity = ((workspace.CurrentCamera.CoordinateFrame.lookVector * (lCONTROL.F + lCONTROL.B)) + ((workspace.CurrentCamera.CoordinateFrame * CFrame.new(lCONTROL.L + lCONTROL.R, (lCONTROL.F + lCONTROL.B) * 0.2, 0).p) - workspace.CurrentCamera.CoordinateFrame.p)) * SPEED
			else
			BV.velocity = Vector3.new(0, 0.1, 0)
			end
			BG.cframe = workspace.CurrentCamera.CoordinateFrame
					until not flying
					CONTROL = {F = 0, B = 0, L = 0, R = 0}
					lCONTROL = {F = 0, B = 0, L = 0, R = 0}
					SPEED = 0
					BG:destroy()
					BV:destroy()
					lplayer.Character.Humanoid.PlatformStand = false
				end)
			end
		Mouse.KeyDown:connect(function(KEY)
			if KEY:lower() == 'w' then
				CONTROL.F = speedfly
			elseif KEY:lower() == 's' then
				CONTROL.B = -speedfly
			elseif KEY:lower() == 'a' then
				CONTROL.L = -speedfly 
			elseif KEY:lower() == 'd' then 
				CONTROL.R = speedfly
			end
		end)
		Mouse.KeyUp:connect(function(KEY)
			if KEY:lower() == 'w' then
				CONTROL.F = 0
			elseif KEY:lower() == 's' then
				CONTROL.B = 0
			elseif KEY:lower() == 'a' then
				CONTROL.L = 0
			elseif KEY:lower() == 'd' then
				CONTROL.R = 0
			end
		end)
		fly()
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("unfly") then
			flying = false
			lplayer.Character.Humanoid.PlatformStand = false
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("chat ") then
			game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer((string.sub(CMDBAR.Text, 6)), "All")
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("spam ") then
			spamtext = (string.sub(CMDBAR.Text, 6))
			spamming = true
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("unspam") then
			spamming = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("spamwait ") then
			spamdelay = (string.sub(CMDBAR.Text, 10))
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("pmspam ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
				pmspammed = v.Name
				spammingpm = true
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("unpmspam") then
			spammingpm = false
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("cfreeze ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 9))) do
				v.Character["Left Leg"].Anchored = true
				v.Character["Left Arm"].Anchored = true
				v.Character["Right Leg"].Anchored = true
				v.Character["Right Arm"].Anchored = true
				v.Character.Torso.Anchored = true
				v.Character.Head.Anchored = true
			end
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("uncfreeze ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 11))) do
				v.Character["Left Leg"].Anchored = false
				v.Character["Left Arm"].Anchored = false
				v.Character["Right Leg"].Anchored = false
				v.Character["Right Arm"].Anchored = false
				v.Character.Torso.Anchored = false
				v.Character.Head.Anchored = false
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("unlockws") then
			local a = game:GetService("Workspace"):getChildren()
			for i = 1, #a do
				if a[i].className == "Part" then
					a[i].Locked = false
				elseif a[i].className == "Model" then
					local r = a[i]:getChildren()
					for i = 1, #r do
						if r[i].className == "Part" then
						r[i].Locked = false
						end
					end
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Success!";
			Text = "Workspace unlocked. Use ;lockws to lock.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("lockws") then
			local a = game:GetService("Workspace"):getChildren()
			for i = 1, #a do
				if a[i].className == "Part" then
					a[i].Locked = true
				elseif a[i].className == "Model" then
					local r = a[i]:getChildren()
					for i = 1, #r do
						if r[i].className == "Part" then
						r[i].Locked = true
						end
					end
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("btools") then
			local Clone_T = Instance.new("HopperBin",lplayer.Backpack)
			Clone_T.BinType = "Clone"
			local Destruct = Instance.new("HopperBin",lplayer.Backpack)
			Destruct.BinType = "Hammer"
			local Hold_T = Instance.new("HopperBin",lplayer.Backpack)
			Hold_T.BinType = "Grab"
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("pstand") then
			lplayer.Character.Humanoid.PlatformStand = true
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("unpstand") then
			lplayer.Character.Humanoid.PlatformStand = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("blockhead") then
			lplayer.Character.Head.Mesh:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("sit") then
			lplayer.Character.Humanoid.Sit = true
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("bringobj ") then
			local function bringobjw()
			for i,obj in ipairs(game:GetService("Workspace"):GetDescendants()) do
			if obj.Name == (string.sub(CMDBAR.Text, 10)) then
			obj.CFrame = lplayer.Character.HumanoidRootPart.CFrame
			obj.CanCollide = false
			obj.Transparency = 0.7
			wait()
			obj.CFrame = lplayer.Character["Left Leg"].CFrame
			wait()
			obj.CFrame = lplayer.Character["Right Leg"].CFrame
			wait()
			obj.CFrame = lplayer.Character["Head"].CFrame
			end
			end
			end
			while wait() do
				bringobjw()
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "BringObj";
			Text = "BringObj enabled.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("wsvis ") then
			vis = (string.sub(CMDBAR.Text, 7))
			local a = game:GetService("Workspace"):GetDescendants()
			for i = 1, #a do
				if a[i].className == "Part" then
					a[i].Transparency = vis
				elseif a[i].className == "Model" then
					local r = a[i]:getChildren()
					for i = 1, #r do
						if r[i].className == "Part" then
						r[i].Transparency = vis
						end
					end
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("hypertotal") then
			loadstring(game:GetObjects("rbxassetid://1255063809")[1].Source)()
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Success!";
			Text = "HyperTotal GUI Loaded!";
			})
		end
		if string.sub(CMDBAR.Text, 1, 4) == ("cmds") then
			CMDSFRAME.Visible = true
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("rmeshhats") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Accessory")) or (v:IsA("Hat")) then
					v.Handle.Mesh:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("blockhats") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Accessory")) or (v:IsA("Hat")) then
					v.Handle.Mesh:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("rmeshtool") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Tool")) then
					v.Handle.Mesh:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("blocktool") then
			for i,v in pairs(lplayer.Character:GetChildren()) do
				if (v:IsA("Tool")) then
					v.Handle.Mesh:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("spinner") then
			local p = Instance.new("RocketPropulsion")
			p.Parent = lplayer.Character.HumanoidRootPart
			p.Name = "Spinner"
			p.Target = lplayer.Character["Left Arm"]
			p:Fire()
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Spinner enabled";
			Text = "Type ;nospinner to disable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("nospinner") then
			lplayer.Character.HumanoidRootPart.Spinner:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("reachd") then
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
				if v:isA("Tool") then
					local a = Instance.new("SelectionBox",v.Handle)
					a.Adornee = v.Handle
					v.Handle.Size = Vector3.new(0.5,0.5,60)
					v.GripPos = Vector3.new(0,0,0)
					lplayer.Character.Humanoid:UnequipTools()
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Reach applied!";
			Text = "Applied to equipped sword. Use ;noreach to disable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("reach ") then
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
				if v:isA("Tool") then
					local a = Instance.new("SelectionBox",v.Handle)
					a.Name = "Reach"
					a.Adornee = v.Handle
					v.Handle.Size = Vector3.new(0.5,0.5,(string.sub(CMDBAR.Text, 7)))
					v.GripPos = Vector3.new(0,0,0)
					lplayer.Character.Humanoid:UnequipTools()
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Reach applied!";
			Text = "Applied to equipped sword. Use ;noreach to disable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("noreach") then
			for i,v in pairs(game:GetService'Players'.LocalPlayer.Character:GetChildren())do
				if v:isA("Tool") then
					v.Handle.Reach:Destroy()
				end
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Reach removed!";
			Text = "Removed reach from equipped sword.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("rkill ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7)))do
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				wait(0.1)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.2)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.5)
				lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(Vector3.new(-100000,10,-100000))
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("tp me ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("cbring ") then
			if (string.sub(CMDBAR.Text, 8)) == "all" or (string.sub(CMDBAR.Text, 8)) == "All" or (string.sub(CMDBAR.Text, 8)) == "ALL" then
				cbringall = true
			else
				for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
					brplr = v.Name
				end
			end
			cbring = true
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("uncbring") then
			cbring = false
			cbringall = false
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("swap ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				local NOWPLR = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				local NOW = lplayer.Character.HumanoidRootPart.CFrame
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				local function tp(player,player2)
				local char1,char2=player.Character,player2.Character
				if char1 and char2 then
				char1:MoveTo(char2.Head.Position)
				end
				end
				wait(0.1)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.2)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character.HumanoidRootPart.CFrame
				wait(0.5)
				lplayer.Character.HumanoidRootPart.CFrame = NOW
				wait(0.6)
				tp(lplayer, game:GetService("Players")[v.Name])
				wait(0.4)
				lplayer.Character.HumanoidRootPart.CFrame = NOWPLR
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("glitch ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
				lplayer.Character.Humanoid.Name = 1
				local l = lplayer.Character["1"]:Clone()
				l.Parent = lplayer.Character
				l.Name = "Humanoid"
				wait(0.1)
				lplayer.Character["1"]:Destroy()
				game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character
				lplayer.Character.Animate.Disabled = true
				wait(0.1)
				lplayer.Character.Animate.Disabled = false
				lplayer.Character.Humanoid.DisplayDistanceType = "None"
				for i,v in pairs(game:GetService'Players'.LocalPlayer.Backpack:GetChildren())do
				lplayer.Character.Humanoid:EquipTool(v)
				end
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
				wait(0.3)
				lplayer.Character.HumanoidRootPart.CFrame = game:GetService("Players")[v.Name].Character["Left Arm"].CFrame
				wait(0.4)
				b = Instance.new("BodyForce")
				b.Parent = lplayer.Character.HumanoidRootPart
				b.Name = "Glitch"
				b.Force = Vector3.new(100000000,5000,0)
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "Tools needed!";
				Text = "You need a tool in your backpack for this command!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("unglitch") then
			lplayer.Character.HumanoidRootPart.Glitch:Destroy()
			lplayer.Character.HumanoidRootPart.CFrame = CFrame.new(10000,0,10000)
			b = Instance.new("BodyForce")
			b.Parent = lplayer.Character.HumanoidRootPart
			b.Name = "unGlitch"
			b.Force = Vector3.new(0,-5000000,0)
			wait(2)
			lplayer.Character.HumanoidRootPart.unGlitch:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("grespawn") then
			lplayer.Character.Humanoid.Health = 0
			wait(1)
			lplayer.Character.Head.CFrame = CFrame.new(1000000,0,1000000)
			lplayer.Character.Torso.CFrame = CFrame.new(1000000,0,1000000)
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("explorer") then
			loadstring(game:GetObjects("rbxassetid://492005721")[1].Source)()
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Success!";
			Text = "DEX Explorer has loaded.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("anim ") then
			local Anim = Instance.new("Animation")
			Anim.AnimationId = "rbxassetid://"..(string.sub(CMDBAR.Text, 6))
			local track = lplayer.Character.Humanoid:LoadAnimation(Anim)
			track:Play(.1, 1, 1)
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("animgui") then
			loadstring(game:GetObjects("rbxassetid://1202558084")[1].Source)()
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Success!";
			Text = "Energize Animations GUI has loaded.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("savepos") then
			saved = lplayer.Character.HumanoidRootPart.CFrame
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Position Saved";
			Text = "Use ;loadpos to return to saved position.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("loadpos") then
			lplayer.Character.HumanoidRootPart.CFrame = saved
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("bang ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				local Anim2 = Instance.new("Animation")
				Anim2.AnimationId = "rbxassetid://148840371"
				local track2 = lplayer.Character.Humanoid:LoadAnimation(Anim2)
				track2:Play(.1, 1, 1)
				bplrr = v.Name
				banpl = true
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("unbang") then
			banpl = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("bringmod ") then
			local function bringmodw()
			for i,obj in ipairs(game:GetService("Workspace"):GetDescendants()) do
			if obj.Name == (string.sub(CMDBAR.Text, 10)) then
			for i,ch in pairs(obj:GetDescendants()) do
			if (ch:IsA("BasePart")) then
			ch.CFrame = lplayer.Character.HumanoidRootPart.CFrame
			ch.CanCollide = false
			ch.Transparency = 0.7
			wait()
			ch.CFrame = lplayer.Character["Left Leg"].CFrame
			wait()
			ch.CFrame = lplayer.Character["Right Leg"].CFrame
			wait()
			ch.CFrame = lplayer.Character["Head"].CFrame
			end
			end
			end
			end
			end
			while wait() do
				bringmodw()
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "BringMod";
			Text = "BringMod enabled.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("respawn") then
			local mod = Instance.new('Model', workspace) mod.Name = 're '..lplayer.Name
			local hum = Instance.new('Humanoid', mod)
			local ins = Instance.new('Part', mod) ins.Name = 'Torso' ins.CanCollide = false ins.Transparency = 1
			lplayer.Character = mod
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("shutdown") then
			game:GetService'RunService'.Stepped:Connect(function()
			pcall(function()
			    for i,v in pairs(game:GetService'Players':GetPlayers()) do
			        if v.Character ~= nil and v.Character:FindFirstChild'Head' then
			            for _,x in pairs(v.Character.Head:GetChildren()) do
			                if x:IsA'Sound' then x.Playing = true x.CharacterSoundEvent:FireServer(true, true) end
			            end
			        end
			    end
			end)
			end)
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Attempting Shutdown";
			Text = "Shutdown Attempt has begun.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("delobj ") then
			objtodel = (string.sub(CMDBAR.Text, 8))
			for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
				if v.Name == objtodel then
					v:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("getplrs") then
			for i,v in pairs(game:GetService("Players"):GetPlayers())do
				print(v)
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Printed";
			Text = "Players have been printed to console. (F9)";
			})
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("deldecal") then
			for i,v in pairs(game:GetService("Workspace"):GetDescendants())do
				if (v:IsA("Decal")) then
					v:Destroy()
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 10) == ("opfinality") then
			loadstring(game:GetObjects("rbxassetid://1294358929")[1].Source)()
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Success!";
			Text = "OpFinality GUI has loaded.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("remotes") then
			remotes = true
			added = true
			game.DescendantAdded:connect(function(rmt)
			if added == true then
			if remotes == true then 
			if rmt:IsA("RemoteEvent") then
			print("A RemoteEvent was added!")
			print(" game." .. rmt:GetFullName() .. " | RemoteEvent")
			print(" game." .. rmt:GetFullName() .. " | RemoteEvent", 247, 0, 0, true)
			end end end
			end)
			game.DescendantAdded:connect(function(rmtfnctn)
			if added == true then
			if remotes == true then 
			if rmtfnctn:IsA("RemoteFunction") then
			warn("A RemoteFunction was added!")
			warn(" game." .. rmtfnctn:GetFullName() .. " | RemoteFunction")
			print(" game." .. rmtfnctn:GetFullName() .. " | RemoteFunction", 5, 102, 198, true)
			end end end
			end)
			
			game.DescendantAdded:connect(function(bndfnctn)
			if added == true then
			if binds == true then 
			if bndfnctn:IsA("BindableFunction") then
			print("A BindableFunction was added!")
			print(" game." .. bndfnctn:GetFullName() .. " | BindableFunction")
			print(" game." .. bndfnctn:GetFullName() .. " | BindableFunction", 239, 247, 4, true)
			end end end
			end)
			
			game.DescendantAdded:connect(function(bnd)
			if added == true then
			if binds == true then 
			if bnd:IsA("BindableEvent") then
			warn("A BindableEvent was added!")
			warn(" game." .. bnd:GetFullName() .. " | BindableEvent")
			print(" game." .. bnd:GetFullName() .. " | BindableEvent", 13, 193, 22, true)
			end end end
			end)
			
			
			if binds == true then
			for i,v in pairs(game:GetDescendants()) do
			if v:IsA("BindableFunction") then
			print(" game." .. v:GetFullName() .. " | BindableFunction")
			print(" game." .. v:GetFullName() .. " | BindableFunction", 239, 247, 4, true)
			end end
			for i,v in pairs(game:GetDescendants()) do
			if v:IsA("BindableEvent") then
			warn(" game." .. v:GetFullName() .. " | BindableEvent")
			print(" game." .. v:GetFullName() .. " | BindableEvent", 13, 193, 22, true)
			end end
			else
			print("Off")
			end
			if remotes == true then
			for i,v in pairs(game:GetDescendants()) do
			if v:IsA("RemoteFunction") then
			warn(" game." .. v:GetFullName() .. " | RemoteFunction")
			print(" game." .. v:GetFullName() .. " | RemoteFunction", 5, 102, 198, true)
			end end
			wait()
			for i,v in pairs(game:GetDescendants()) do
			if v:IsA("RemoteEvent") then
			print(" game." .. v:GetFullName() .. " | RemoteEvent")
			print(" game." .. v:GetFullName() .. " | RemoteEvent", 247, 0, 0, true)
			end end
			else
			print("Off")
			end
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Printing Remotes";
			Text = "Type ;noremotes to disable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("noremotes") then
			remotes = false
			added = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Printing Remotes Disabled";
			Text = "Type ;remotes to enable.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("tpdefault") then
			spin = false
			followed = false
			traill = false
			noclip = false
			annoying = false
			hwalk = false
			cbringing = false
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("stopsit") then
			stopsitting = true
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("gosit") then
			stopsitting = false
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("version") then
			print(adminversion)
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Version";
			Text = adminversion;
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("clicktp") then
			clickgoto = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Click TP";
			Text = "Press E to teleport to mouse position";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("noclicktp") then
			clickgoto = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Click TP";
			Text = "Click TP has been disabled.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("toolson") then
			gettingtools = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools Enabled";
			Text = "Automatically colleting tools dropped.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("toolsoff") then
			gettingtools = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Tools Disabled";
			Text = "Click TP has been disabled.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("delcmdbar") then
			ScreenGui:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 5) == ("reset") then
			lplayer.Character.Head:Destroy()
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("state ") then
			statechosen = string.sub(CMDBAR.Text, 7)
			changingstate = true
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("gravity ") then
			game:GetService("Workspace").Gravity = string.sub(CMDBAR.Text, 9)
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("looprhats") then
		removingmeshhats = true
		end
		if string.sub(CMDBAR.Text, 1, 11) == ("unlooprhats") then
			removingmeshhats = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("looprtool") then
			removingmeshtool = true
		end
		if string.sub(CMDBAR.Text, 1, 11) == ("unlooprtool") then
			removingmeshtool = false
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("givetool ") then
			for i,v in pairs(game:GetService("Players").LocalPlayer.Character:GetDescendants()) do
				if v:IsA("Tool") then
					for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 10))) do
						v.Parent = player.Character
					end
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 4) == ("age ") then
			for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 5))) do
				game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(player.Name.." Account Age: "..player.AccountAge.." days!", "All")
			end
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("id ") then
			for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 4))) do
				game:GetService("ReplicatedStorage").DefaultChatSystemChatEvents.SayMessageRequest:FireServer(player.Name.." Account ID: "..player.UserId, "All")
			end
		end
		if string.sub(CMDBAR.Text, 1, 5) == (".age ") then
			for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 6))) do
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = player.AccountAge.." Days";
				Text = "Account age of "..player.Name;
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 4) == (".id ") then
			for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 5))) do
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = player.UserId.." ID";
				Text = "Account ID of "..player.Name;
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("gameid") then
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "Game ID";
			Text = "Game ID: ".. game.GameId;
			})
		end
		if string.sub(CMDBAR.Text, 1, 3) == ("pgs") then
			local pgscheck = game:GetService("Workspace"):PGSIsEnabled()
			if pgscheck == true then
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "PGSPhysicsSolverEnabled";
				Text = "PGS is Enabled!";
				})
			else
				game:GetService("StarterGui"):SetCore("SendNotification", {
				Title = "PGSPhysicsSolverEnabled";
				Text = "PGS is Disabled!";
				})
			end
		end
		if string.sub(CMDBAR.Text, 1, 11) == ("removeinvis") then
			for i,v in pairs(game:GetService("Workspace"):GetDescendants()) do
				if v:IsA("Part") then
					if v.Transparency == 1 then
						if v.Name ~= "HumanoidRootPart" then
							v:Destroy()
						end
					end
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("removefog") then
			game:GetService("Lighting").FogStart = 0
			game:GetService("Lighting").FogEnd = 9999999999999
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("disable") then
			lplayer.Character.Humanoid.Parent = lplayer
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("enable") then
			lplayer.Humanoid.Parent = lplayer.Character
		end
		if string.sub(CMDBAR.Text, 1, 13) == ("givealltools ") then
			for i,v in pairs(game:GetService("Players").LocalPlayer.Backpack:GetDescendants()) do
				if v:IsA("Tool") then
					v.Parent = lplayer.Character
					wait()
					for i,player in pairs(GetPlayer(string.sub(CMDBAR.Text, 14))) do
						v.Parent = player.Character
					end
				end
			end
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("flyspeed ") then
			speedfly = string.sub(CMDBAR.Text, 10)
			wait()
			change()
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("carpet ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 8))) do
				local Anim3 = Instance.new("Animation")
				Anim3.AnimationId = "rbxassetid://282574440"
				local track3 = lplayer.Character.Humanoid:LoadAnimation(Anim3)
				track3:Play(.1, 1, 1)
				bplrr = v.Name
				banpl = true
			end
		end
		if string.sub(CMDBAR.Text, 1, 8) == ("uncarpet") then
			banpl = false
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("stare ") then
			for i,v in pairs(GetPlayer(string.sub(CMDBAR.Text, 7))) do
				staring = true
				stareplr = v
			end
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("unstare") then
			staring = false
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("logchat") then
			chatlogs = true
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "LogChat enabled";
			Text = "Now logging all player chat.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 9) == ("unlogchat") then
			chatlogs = false
			game:GetService("StarterGui"):SetCore("SendNotification", {
			Title = "LogChat disabled";
			Text = "Stopped logging all player chat.";
			})
		end
		if string.sub(CMDBAR.Text, 1, 6) == ("fixcam") then
			game:GetService("Workspace").CurrentCamera:Destroy()
			wait(0.1)
			game:GetService("Workspace").CurrentCamera.CameraSubject = lplayer.Character.Humanoid
			game:GetService("Workspace").CurrentCamera.CameraType = "Custom"
			lplayer.CameraMinZoomDistance = 0.5
			lplayer.CameraMaxZoomDistance = 400
			lplayer.CameraMode = "Classic"
		end
		if string.sub(CMDBAR.Text, 1, 7) == ("unstate") then
			changingstate = false
		end
		CMDBAR.Text = ""
	end
end)

wait(0.3)
game:GetService("StarterGui"):SetCore("SendNotification", {
	Title = "Loaded successfully!";
	Text = "Reviz Admin V2 by illremember";
})
wait(0.1)
print("Reviz Admin V2 loaded!")
if game:GetService("Workspace").FilteringEnabled == true then
	warn("FE is Enabled (Filtering Enabled)")
	game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "FE is Enabled";
		Text = "Filtering Enabled. Enjoy using Reviz Admin!";
	})
else
	warn("FE is Disabled (Filtering Disabled) Consider using a different admin script.")
	game:GetService("StarterGui"):SetCore("SendNotification", {
		Title = "FE is Disabled";
		Text = "Filtering Disabled. Consider using a different admin script.";
	})
end

local intro = Instance.new("ScreenGui")
local Frame = Instance.new("Frame")
local ImageLabel = Instance.new("ImageLabel")
intro.Parent = game:GetService("CoreGui")
Frame.Parent = intro
Frame.BackgroundColor3 = Color3.new(1, 1, 1)
Frame.BackgroundTransparency = 1
Frame.Size = UDim2.new(1, 0, 0, 300)
Frame.Position = UDim2.new(0, 0, -0.4, 0)
ImageLabel.Parent = Frame
ImageLabel.BackgroundColor3 = Color3.new(1, 1, 1)
ImageLabel.BackgroundTransparency = 1
ImageLabel.Position = UDim2.new(0, 0, 0, 0)
ImageLabel.Size = UDim2.new(1, 0, 1, 0)
ImageLabel.Image = "http://www.roblox.com/asset/?id=1542162618"
Frame:TweenPosition(UDim2.new(0, 0, 0.2, 0), "Out", "Elastic", 3)
wait(3.01)
Frame:TweenPosition(UDim2.new(0, 0, 1.5, 0), "Out", "Elastic", 5)
wait(5.01)
intro:Destroy()

