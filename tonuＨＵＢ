local gs=game local p=gs:GetService("Players")local rs=gs:GetService("RunService")local cam=workspace.CurrentCamera local lp=p.LocalPlayer
cam.FieldOfView=120

local o=loadstring(gs:HttpGet('https://raw.githubusercontent.com/jensonhirst/Orion/main/source'))()

local a,b,c,d,e,f,g,h,i,j,k=false,false,false,false,false,false,16,Color3.fromRGB(255,60,60),2,12,{}

local s=Instance.new("Sound")s.SoundId="rbxassetid://9043887091"s.Volume=0.9 s.Parent=workspace s:Play()s.Ended:Connect(function()s:Destroy()end)

local w=o:MakeWindow({Name="tonuHUB β",HidePremium=false,SaveConfig=true,ConfigFolder="tM",IntroEnabled=true,IntroText="tonuHUB β"})

local m=w:MakeTab({Name="メイン",Icon="rbxassetid://4483345998",PremiumOnly=false})

m:AddButton({Name="視点切替",Callback=function()a=not a if a then lp.CameraMode=Enum.CameraMode.LockFirstPerson else lp.CameraMode=Enum.CameraMode.Classic lp.CameraMinZoomDistance=0.5 lp.CameraMaxZoomDistance=400 end end})

m:AddToggle({Name="線ESP",Default=false,Callback=function(v)b=v end})
m:AddToggle({Name="強化A",Default=false,Callback=function(v)c=v end})
m:AddToggle({Name="S",Default=false,Callback=function(v)d=v end})
m:AddToggle({Name="∞J",Default=false,Callback=function(v)e=v end})

m:AddSlider({Name="WS",Min=16,Max=100,Default=16,Increment=1,Callback=function(v)g=v end})
m:AddTextbox({Name="WS入力",Default="16",TextDisappear=false,Callback=function(v)local n=tonumber(v)if n then g=n end end})

local es=w:MakeTab({Name="ESP",Icon="rbxassetid://6031094678",PremiumOnly=false})

es:AddDropdown({Name="色",Default="赤",Options={"赤","青","緑","黄色","紫","白","ピンク"},Callback=function(v)if v=="赤"then h=Color3.fromRGB(255,60,60)elseif v=="青"then h=Color3.fromRGB(0,170,255)elseif v=="緑"then h=Color3.fromRGB(0,255,100)elseif v=="黄色"then h=Color3.fromRGB(255,255,0)elseif v=="紫"then h=Color3.fromRGB(180,0,255)elseif v=="白"then h=Color3.fromRGB(255,255,255)elseif v=="ピンク"then h=Color3.fromRGB(255,100,200)end end})

es:AddTextbox({Name="太さ",Default="2",TextDisappear=false,Callback=function(v)local n=tonumber(v)if n then i=math.clamp(n,1,10)end end})
es:AddTextbox({Name="Sサイズ(5-100)",Default="12",TextDisappear=false,Callback=function(v)local n=tonumber(v)if n then j=math.clamp(n,5,100)end end})

local gr=w:MakeTab({Name="グラブ",Icon="rbxassetid://6031094678",PremiumOnly=false})

gr:AddToggle({Name="AK",Default=false,Callback=function(v)f=v if v then lp.Kick=function()end hookmetamethod(game,"__namecall",function(self,...)if getnamecallmethod():lower()=="kick"then return end return self[getnamecallmethod()](self,...)end) o:MakeNotification({Name="AK",Content="有効",Time=4})end end})

gs:GetService("UserInputService").JumpRequest:Connect(function()if e and lp.Character and lp.Character:FindFirstChild("Humanoid")then lp.Character.Humanoid:ChangeState("Jumping")end end)

rs.RenderStepped:Connect(function()if lp.Character and lp.Character:FindFirstChild("Humanoid")then lp.Character.Humanoid.WalkSpeed=g end end)

local function ct()local l=Drawing.new("Line")l.Thickness=i l.Color=h l.Transparency=0.85 l.Visible=false return l end

rs.RenderStepped:Connect(function()
	if not b then for _,l in pairs(k)do if l then l.Visible=false end end return end
	for _,pl in ipairs(p:GetPlayers())do
		if pl~=lp and pl.Character and pl.Character:FindFirstChild("HumanoidRootPart")then
			local r=pl.Character.HumanoidRootPart local pos,on=cam:WorldToViewportPoint(r.Position+Vector3.new(0,2,0))
			if not k[pl]then k[pl]=ct()end local l=k[pl]
			l.Thickness=i l.Color=h
			if on and pos.Z>0 then
				l.From=Vector2.new(cam.ViewportSize.X/2,cam.ViewportSize.Y/2)
				l.To=Vector2.new(pos.X,pos.Y)
				l.Visible=true
			else l.Visible=false end
		end
	end
end)

local t=0
rs.RenderStepped:Connect(function()
	if not d then return end
	if tick()-t<0.15 then return end t=tick()
	for _,pl in ipairs(p:GetPlayers())do
		if pl~=lp and pl.Character then
			local r=pl.Character:FindFirstChild("HumanoidRootPart")
			if r then
				local dist=(r.Position-(lp.Character and lp.Character:FindFirstChild("HumanoidRootPart") and lp.Character.HumanoidRootPart.Position or Vector3.new())).Magnitude
				if dist>80 then continue end
				local sz=j+math.random(-4,4) sz=math.clamp(sz,5,100)
				r.Size=Vector3.new(sz,sz,sz)
				r.Transparency=1
				r.CanCollide=false
				r.Material=Enum.Material.Plastic
			end
		end
	end
end)

o:MakeNotification({Name="tonuHUB β",Content="ロード完了",Time=5})
print("tHβ loaded")
