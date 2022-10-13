--[[VARIABLE DEFINITION ANOMALY DETECTED, DECOMPILATION OUTPUT POTENTIALLY INCORRECT]]--
-- Decompiled with the Synapse X Luau decompiler.

local l__RunService__1 = game:GetService("RunService");
local l__ReplicatedStorage__2 = game:GetService("ReplicatedStorage");
local l__UserInputService__3 = game:GetService("UserInputService");
local l__StarterGui__4 = game:GetService("StarterGui");
local l__Debris__5 = game:GetService("Debris");
local l__TweenService__6 = game:GetService("TweenService");
local l__Lighting__7 = game:GetService("Lighting");
local l__MarketplaceService__8 = game:GetService("MarketplaceService");
local l__ContentProvider__9 = game:GetService("ContentProvider");
local l__ContextActionService__10 = game:GetService("ContextActionService");
local l__TeleportService__11 = game:GetService("TeleportService");
local v12 = {};
local l__next__13 = next;
local v14, v15 = workspace.SpawnParts:GetChildren();
while true do
	local v16, v17 = l__next__13(v14, v15);
	if not v16 then
		break;
	end;
	v15 = v16;
	v12[#v12 + 1] = CFrame.new(v17.CFrame.p);
end;
l__Lighting__7.Bloom.Intensity = 1;
l__Lighting__7.Bloom.Size = 13;
l__StarterGui__4:SetCoreGuiEnabled(Enum.CoreGuiType.Backpack, false);
l__StarterGui__4:SetCoreGuiEnabled(Enum.CoreGuiType.Health, false);
l__StarterGui__4:SetCoreGuiEnabled(Enum.CoreGuiType.PlayerList, false);
coroutine.wrap(function()
	while not pcall(game.StarterGui.SetCore, game.StarterGui, "TopbarEnabled", false) and tick() - tick() < 1 do
		wait();	
	end;
end)();
local v18 = Instance.new("BindableEvent");
v18.Event:connect(function()
	if game.Players.LocalPlayer.Character.Head:FindFirstChild("LogNotice") then
		functionBank.CreateNotification("You can't reset in combat", Color3.fromRGB(255, 0, 0), 4);
		return;
	end;
	game.Players.LocalPlayer.Character:BreakJoints();
end);
coroutine.wrap(function()
	wait();
	l__StarterGui__4:SetCore("ResetButtonCallback", v18);
end)();
local v19 = require(l__ReplicatedStorage__2.Modules.ColorData);
local v20 = require(l__ReplicatedStorage__2.Modules.ItemData);
local v21 = require(l__ReplicatedStorage__2.Modules.GamepassData);
local v22 = require(l__ReplicatedStorage__2.Modules.LevelData);
local v23 = require(l__ReplicatedStorage__2.Modules.CosmeticData);
local v24 = require(l__ReplicatedStorage__2.Modules.AmbientData);
local l__LocalPlayer__25 = game.Players.LocalPlayer;
local l__mouse__26 = l__LocalPlayer__25:GetMouse();
local v27 = Vector3.new(25, 17, -25);
local v28 = Instance.new("Part");
v28.Transparency = 1;
v28.CanCollide = false;
v28.Anchored = true;
v28.Touched:connect(function()

end);
ping = 0;
_G.data = l__ReplicatedStorage__2.Events.RequestData:InvokeServer();
game:GetService("ContentProvider"):PreloadAsync(game.ReplicatedStorage.Animations:GetChildren());
local l__PlayerGui__29 = l__LocalPlayer__25:WaitForChild("PlayerGui");
l__PlayerGui__29:SetTopbarTransparency(1);
local l__MainGui__30 = l__PlayerGui__29:WaitForChild("MainGui");
local l__SecondaryGui__31 = l__PlayerGui__29:WaitForChild("SecondaryGui");
local l__SpawnGui__32 = l__PlayerGui__29:WaitForChild("SpawnGui");
l__LocalPlayer__25:WaitForChild("Backpack").ChildAdded:connect(function()
	l__LocalPlayer__25:Kick();
end);
bodyColorList = {
	LeftUpperLeg = true, 
	LeftLowerLeg = true, 
	LeftFoot = true, 
	RightUpperLeg = true, 
	RightLowerLeg = true, 
	RightFoot = true, 
	UpperTorso = true, 
	LowerTorso = true
};
skinColorList = {
	LeftUpperArm = true, 
	LeftLowerArm = true, 
	LeftHand = true, 
	RightUpperArm = true, 
	RightLowerArm = true, 
	RightHand = true, 
	Head = true
};
if not l__UserInputService__3.MouseEnabled then
	print("MOUSE NOT DETECTED");
	l__MainGui__30.Panels.Stats.SpellImage.ImageButton.TouchTap:connect(function()
		print("TAPPED");
		local v33, v34, v35, v36 = functionBank.CursorRay();
		l__ReplicatedStorage__2.Events.VoodooSpell:FireServer(v34);
	end);
else
	print("MOUSE DETECTED");
	l__MainGui__30.Panels.Stats.SpellImage.ImageButton.Activated:connect(function()
		print("CLICKED");
		local v37, v38, v39, v40 = functionBank.CursorRay();
		l__ReplicatedStorage__2.Events.VoodooSpell:FireServer(v38);
	end);
end;
local l__next__41 = next;
local v42, v43 = l__MainGui__30.Panels.VoodooSelect.List:GetChildren();
while true do
	local v44, v45 = l__next__41(v42, v43);
	if not v44 then
		break;
	end;
	v43 = v44;
	if v45:IsA("ImageButton") then
		v45.Activated:connect(function()
			l__MainGui__30.Panels.VoodooSelect.Chosen.Value = v45.Name;
			l__MainGui__30.Panels.VoodooSelect.DescFrame.DescText.Text = v20[v45.Name].description;
			local l__next__46 = next;
			local v47, v48 = l__MainGui__30.Panels.VoodooSelect.List:GetChildren();
			while true do
				local v49, v50 = l__next__46(v47, v48);
				if not v49 then
					break;
				end;
				v48 = v49;
				if v50:IsA("ImageButton") and v50 ~= v45 then
					v50.BackgroundColor3 = Color3.fromRGB(0, 0, 0);
				elseif v50 == v45 then
					v50.BackgroundColor3 = Color3.fromRGB(200, 200, 200);
				end;			
			end;
		end);
	end;
end;
l__MainGui__30.Panels.VoodooSelect.ConfirmButton.Activated:connect(function()
	local l__Value__51 = l__MainGui__30.Panels.VoodooSelect.Chosen.Value;
	if l__Value__51 and l__Value__51 ~= "" then
		l__ReplicatedStorage__2.Events.PromptSpellChoice:FireServer(l__Value__51);
		l__MainGui__30.Panels.VoodooTutorial.Visible = true;
		l__MainGui__30.Panels.VoodooSelect.Visible = false;
	end;
end);
l__MainGui__30.Panels.VoodooTutorial.ExitButton.Activated:connect(function()
	l__MainGui__30.Panels.VoodooTutorial.Visible = false;
end);
l__MainGui__30.Panels.UpdateNotifier.Backdrop.ConfirmButton.Activated:connect(function()
	l__MainGui__30.Panels.UpdateNotifier.Visible = false;
end);
l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ExitButton.Activated:connect(function()
	l__MainGui__30.Panels.PurchaseConfirm.Visible = false;
end);
l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ExitButton.Activated:connect(function()
	l__MainGui__30.Panels.ConfirmPurchaseYe.Visible = false;
end);
l__MainGui__30.Panels.Info.Backdrop.ExitButton.Activated:connect(function()
	l__MainGui__30.Panels.Info.Visible = false;
end);
l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ConfirmButton.Activated:connect(function()
	l__ReplicatedStorage__2.Events.PurchaseCosmetic:FireServer(l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.LastSelected.Value);
	l__MainGui__30.Panels.ConfirmPurchaseYe.Visible = false;
end);
l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ConfirmButton.Activated:connect(function()
	l__ReplicatedStorage__2.Events.PurchaseMojoItem:FireServer(l__MainGui__30.Panels.PurchaseConfirm.Backdrop.LastSelected.Value);
	l__MainGui__30.Panels.PurchaseConfirm.Visible = false;
end);
local l__next__52 = next;
local v53, v54 = l__MainGui__30.LeftPanel.Mojo.Lists.MojoList:GetChildren();
while true do
	local v55, v56 = l__next__52(v53, v54);
	if not v55 then
		break;
	end;
	v54 = v55;
	if v56:IsA("Frame") then
		local v57 = v20[v56.Name];
		if v57.toggleable then
			v56.TextButton.Activated:connect(function()
				l__ReplicatedStorage__2.Events.ToggleMojo:FireServer(v56.Name);
			end);
		end;
		v56.ImageButton.Activated:connect(function()
			if functionBank.HasMojoRecipe(v56.Name) then
				functionBank.CreateNotification("You already own this", Color3.fromRGB(255, 255, 111), 2);
				return;
			end;
			l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ItemDescription.Text = v57.description;
			l__MainGui__30.Panels.PurchaseConfirm.Backdrop.LastSelected.Value = v56.Name;
			l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ItemNameLabel.Text = string.upper(v56.Name);
			l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ImageLabel.Image = v57.image;
			if v57.mojoCost then
				if v57.mojoCost > 1 then
					l__MainGui__30.Panels.PurchaseConfirm.Backdrop.MojoCost.Text = v57.mojoCost .. " mojo points";
				elseif v57.mojoCost == 1 then
					l__MainGui__30.Panels.PurchaseConfirm.Backdrop.MojoCost.Text = v57.mojoCost .. " mojo point";
				end;
				l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ConfirmButton.Visible = true;
			else
				l__MainGui__30.Panels.PurchaseConfirm.Backdrop.MojoCost.Text = "Event Item - Not For Sale";
				l__MainGui__30.Panels.PurchaseConfirm.Backdrop.ConfirmButton.Visible = false;
			end;
			l__MainGui__30.Panels.PurchaseConfirm.Visible = true;
		end);
	end;
end;
l__MainGui__30.Panels.MojoConfirm.LevelUpFrame.ExitButton.Activated:connect(function()
	l__MainGui__30.Panels.MojoConfirm.Visible = false;
end);
l__MainGui__30.Panels.MojoConfirm.LevelUpFrame.ConfirmButton.Activated:connect(function()
	l__MainGui__30.Panels.MojoConfirm.Visible = false;
	l__ReplicatedStorage__2.Events.Rebirth:FireServer();
end);
l__MainGui__30.LeftPanel.Mojo.RebirthButton.Activated:connect(function()
	l__MainGui__30.Panels.MojoConfirm.Visible = true;
	if l__MarketplaceService__8:UserOwnsGamePassAsync(l__LocalPlayer__25.UserId, 85943200) then
		l__MainGui__30.Panels.MojoConfirm.LevelUpFrame.MultiplierNext.Text = "(OWNS GAMEPASS) +2 Mojo Point";
		return;
	end;
	l__MainGui__30.Panels.MojoConfirm.LevelUpFrame.MultiplierNext.Text = "+1 Mojo Point";
end);
l__MainGui__30.Panels.Unban.Backdrop.YesButton.Activated:connect(function()
	l__MarketplaceService__8:PromptProductPurchase(l__LocalPlayer__25, 253832340);
end);
local u1 = nil;
l__MainGui__30.LeftPanel.NewTribe.Frame.CreateButton.InputBegan:connect(function(p1, p2)
	if functionBank.InteractInput(p1, p2) and u1 then
		l__ReplicatedStorage__2.Events.CreateTribe:FireServer(u1, "yeet");
		l__ReplicatedStorage__2.LocalSounds.Quicks.TribeSound:Play();
		functionBank.DrawTribeGui();
	end;
end);
l__MainGui__30.LeftPanel.Tribe.LeaveButton.InputBegan:connect(function(p3, p4)
	if functionBank.InteractInput(p3, p4) then
		l__ReplicatedStorage__2.Events.TribeLeave:FireServer();
	end;
end);
l__MainGui__30.LeftPanel.Tribe.TotemButton.InputBegan:connect(function(p5, p6)
	if functionBank.InteractInput(p5, p6) then
		local v58, v59 = functionBank.IsInTribe();
		if v59 and v59.chief == l__LocalPlayer__25.Name then
			if not workspace.Totems:FindFirstChild(v59.color .. " Tribe") then
				functionBank.BindMouseStructure((l__ReplicatedStorage__2.Deployables["Tribe Totem"]:Clone()));
				return;
			end;
		else
			functionBank.CreateNotification("Only the Chief can make a Totem!", v19.badRed, 2);
		end;
	end;
end);
local l__next__60 = next;
local v61, v62 = l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection:GetChildren();
while true do
	local v63, v64 = l__next__60(v61, v62);
	if not v63 then
		break;
	end;
	v62 = v63;
	if v64:IsA("ImageButton") then
		v64.InputBegan:connect(function(p7, p8)
			if functionBank.InteractInput(p7, p8) and _G.data.armor[v64.Name] and _G.data.armor[v64.Name] ~= "none" then
				l__ReplicatedStorage__2.Events.UnequipArmor:FireServer(_G.data.armor[v64.Name]);
			end;
		end);
	end;
end;
l__SecondaryGui__31.PlayerList.List.ActionPanel.KickButton.InputBegan:connect(function(p9, p10)
	if functionBank.InteractInput(p9, p10) then
		local l__Value__65 = l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value;
		if l__Value__65 then
			local v66 = game.Players:FindFirstChild(l__Value__65);
			if v66 then
				l__ReplicatedStorage__2.Events.TribeKick:FireServer(v66);
				l__SecondaryGui__31.PlayerList.List.ActionPanel.Visible = false;
			end;
		end;
	end;
end);
l__SecondaryGui__31.PlayerList.List.ActionPanel.CancelButton.InputBegan:connect(function(p11, p12)
	if functionBank.InteractInput(p11, p12) then
		l__SecondaryGui__31.PlayerList.List.ActionPanel.Visible = false;
	end;
end);
l__SecondaryGui__31.PlayerList.List.ActionPanel.InviteButton.InputBegan:connect(function(p13, p14)
	if functionBank.InteractInput(p13, p14) then
		l__ReplicatedStorage__2.Events.TribeInvite:FireServer(game.Players:FindFirstChild(l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value));
		l__SecondaryGui__31.PlayerList.List.ActionPanel.Visible = false;
	end;
end);
l__MainGui__30.Mobile.StructureButton.InputBegan:connect(function(p15, p16)
	if functionBank.InteractInput(p15, p16) then
		PlaceStructureFunction();
	end;
end);
local l__next__67 = next;
local v68, v69 = l__MainGui__30.LeftPanel.Craft.Selection:GetChildren();
while true do
	local v70, v71 = l__next__67(v68, v69);
	if not v70 then
		break;
	end;
	v69 = v70;
	if v71:IsA("ImageButton") then
		v71.InputBegan:connect(function(p17, p18)
			if functionBank.InteractInput(p17, p18) then
				v71.ActiveImage.Visible = true;
				local l__next__72 = next;
				local v73, v74 = l__MainGui__30.LeftPanel.Craft.Selection:GetChildren();
				while true do
					local v75, v76 = l__next__72(v73, v74);
					if not v75 then
						break;
					end;
					v74 = v75;
					if v76:IsA("ImageButton") and v76 ~= v71 then
						v76.ActiveImage.Visible = false;
					end;				
				end;
				functionBank.DrawCraftMenu(v71.Category.Value);
			end;
		end);
	end;
end;
l__MainGui__30.LeftPanel.Craft.SearchBar.Changed:connect(function(p19)
	if p19 == "Text" then
		if l__MainGui__30.LeftPanel.Craft.SearchBar.Text == "" then
			functionBank.DrawCraftMenu("all");
			return;
		end;
		local l__next__77 = next;
		local v78, v79 = l__MainGui__30.LeftPanel.Craft.Selection:GetChildren();
		while true do
			local v80, v81 = l__next__77(v78, v79);
			if not v80 then
				break;
			end;
			v79 = v80;
			if v81:IsA("ImageButton") then
				v81.BackgroundColor3 = v19.ironGrey;
			end;		
		end;
		functionBank.DrawCraftMenu("all", l__MainGui__30.LeftPanel.Craft.SearchBar.Text);
	end;
end);
local l__next__82 = next;
local v83, v84 = l__MainGui__30.RightPanel.Inventory.Selection:GetChildren();
while true do
	local v85, v86 = l__next__82(v83, v84);
	if not v85 then
		break;
	end;
	v84 = v85;
	if v86:IsA("ImageButton") then
		local u2 = "all";
		v86.InputBegan:connect(function(p20, p21)
			if functionBank.InteractInput(p20, p21) then
				v86.ActiveImage.Visible = true;
				local l__next__87 = next;
				local v88, v89 = l__MainGui__30.RightPanel.Inventory.Selection:GetChildren();
				while true do
					local v90, v91 = l__next__87(v88, v89);
					if not v90 then
						break;
					end;
					v89 = v90;
					if v91:IsA("ImageButton") and v91 ~= v86 then
						v91.ActiveImage.Visible = false;
					end;				
				end;
				print("redrawing with category");
				functionBank.DrawInventory(v86.Category.Value);
				u2 = v86.Category.Value;
			end;
		end);
	end;
end;
l__MainGui__30.RightPanel.Inventory.RedoAvatarButton.InputBegan:connect(function(p22, p23)
	if functionBank.InteractInput(p22, p23) then
		l__ReplicatedStorage__2.Events.RedoAvatar:FireServer();
	end;
end);
local l__next__92 = next;
local v93, v94 = l__MainGui__30.LeftPanel.Shop.Lists.ChestList:GetChildren();
while true do
	local v95, v96 = l__next__92(v93, v94);
	if not v95 then
		break;
	end;
	v94 = v95;
	if v96:IsA("Frame") then
		v96.OpenButton.InputBegan:connect(function(p24, p25)
			if functionBank.InteractInput(p24, p25) then
				if v96.OpenButton.Text == "OPEN" then
					l__ReplicatedStorage__2.Events.ChestDrop:FireServer(v96.Name);
					return;
				end;
			else
				return;
			end;
			functionBank.CreateNotification("You don't have any " .. v96.Name .. "s.", v19.badRed, 2);
		end);
		v96.BuyButton.InputBegan:connect(function(p26, p27)
			if functionBank.InteractInput(p26, p27) then
				l__ReplicatedStorage__2.Events.PurchaseChest:FireServer(v96.Name);
			end;
		end);
	end;
end;
local l__next__97 = next;
local v98, v99 = l__MainGui__30.LeftPanel.Shop.Selection:GetChildren();
while true do
	local v100, v101 = l__next__97(v98, v99);
	if not v100 then
		break;
	end;
	v99 = v100;
	if v101:IsA("ImageButton") then
		v101.InputBegan:connect(function(p28, p29)
			if functionBank.InteractInput(p28, p29) then
				print("input on button");
				l__MainGui__30.LeftPanel.Shop.CategoryTitle.Text = v101.Name;
				local l__next__102 = next;
				local v103, v104 = l__MainGui__30.LeftPanel.Shop.Lists:GetChildren();
				while true do
					local v105, v106 = l__next__102(v103, v104);
					if not v105 then
						break;
					end;
					v104 = v105;
					if v106:IsA("Frame") or v106:IsA("ScrollingFrame") then
						if v106 ~= v101.Pointer.Value then
							v106.Visible = false;
						else
							v106.Visible = true;
						end;
					end;				
				end;
				local l__next__107 = next;
				local v108, v109 = l__MainGui__30.LeftPanel.Shop.Selection:GetChildren();
				while true do
					local v110, v111 = l__next__107(v108, v109);
					if not v110 then
						break;
					end;
					v109 = v110;
					if v111:IsA("ImageButton") then
						if v111 ~= v101 then
							v111.BackgroundColor3 = v19.ironGrey;
						else
							v111.BackgroundColor3 = v19.goodGreen;
						end;
					end;				
				end;
			end;
		end);
	end;
end;
function PhaseThing(p30, p31)
	if p31 then
		p30.Parent = workspace;
		return;
	end;
	p30.Parent = l__ReplicatedStorage__2;
end;
local u3 = false;
game.Players.PlayerAdded:connect(function(p32)
	if not p32 == l__LocalPlayer__25 then
		p32.CharacterAdded:connect(function(p33)
			if u3 then
				PhaseThing(p33);
			end;
		end);
	end;
end);
function ToggleOtherCharacters(p34)
	local l__next__112 = next;
	local v113, v114 = game.Players:GetPlayers();
	while true do
		local v115, v116 = l__next__112(v113, v114);
		if v115 then

		else
			break;
		end;
		v114 = v115;
		if v116 ~= l__LocalPlayer__25 then
			if v116.Character then
				PhaseThing(v116.Character, p34);
			end;
		end;	
	end;
end;
local u4 = {};
local u5 = nil;
local u6 = 0;
local u7 = nil;
local u8 = nil;
local u9 = 0;
l__RunService__1.RenderStepped:connect(function(p35)
	for v117, v118 in next, u4 do
		if os.time() - u4[v117].age > 6.5 then
			u4[v117].object:Destroy();
			table.remove(u4, v117);
		else
			local v119 = nil;
			local l__position__120 = u4[v117].position;
			u4[v117].velocity = v118.velocity + v118.acceleration * p35;
			u4[v117].position = v118.position + v118.velocity * p35;
			v119 = u4[v117].position - l__position__120;
			if u4[v117].object:IsA("Model") then
				u4[v117].object:SetPrimaryPartCFrame(CFrame.new(u4[v117].position, u4[v117].position + v119));
			else
				u4[v117].object.CFrame = CFrame.new(u4[v117].position, u4[v117].position + v119);
			end;
			local v121, v122, v123, v124 = workspace:FindPartOnRay(Ray.new(l__position__120, u4[v117].position - l__position__120), u4[v117].object);
			if not (not v121) and (not (not v121.CanCollide) or v121.Transparency < 1) or v121 == workspace.Terrain and not v124 == Enum.Material.Water then
				if u4[v117].owned then
					l__ReplicatedStorage__2.Events.OnBruh:FireServer(v121, v122, u4[v117], (l__LocalPlayer__25.Character.PrimaryPart.Position - v122).magnitude);
					local v125 = nil;
					if (v121:FindFirstChild("Health") or v121.Parent and v121.Parent:FindFirstChild("Health")) and (v121:FindFirstChild("Health") or v121.Parent and v121.Parent:FindFirstChild("Health")):IsA("IntValue") then
						v125 = true;
					end;
					local l__next__126 = next;
					local v127, v128 = game.Players:GetPlayers();
					while true do
						local v129, v130 = l__next__126(v127, v128);
						if not v129 then
							break;
						end;
						v128 = v129;
						if v130.Character and v121:IsDescendantOf(v130.Character) then
							v125 = true;
						end;					
					end;
					if v125 then
						functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.Quicks.HitMarker, l__PlayerGui__29);
					end;
				end;
				l__Debris__5:AddItem(u4[v117].object, 2);
				u4[v117].object.Transparency = 1;
				table.remove(u4, v117);
			end;
		end;
	end;
	if _G.data.userSettings.autoFpickup then
		if u5 then
			if os.clock() - u6 >= 0.25 then
				if not l__mouse__26.Target:FindFirstChild("Pickup") then
					if l__mouse__26.Target.Parent:FindFirstChild("Pickup") and (l__mouse__26.Target.Position - u7.Position).magnitude <= 15 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
						local v131 = nil;
						if l__mouse__26.Target:FindFirstChild("Pickup") then
							v131 = l__mouse__26.Target;
						elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
							v131 = l__mouse__26.Target.Parent;
						end;
						if v131 ~= nil then
							if functionBank.CanBearLoad(v131.Name) then
								l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
								l__ReplicatedStorage__2.Events.Pickup:FireServer(v131);
								if ping <= 0.001 then
									return;
								else
									functionBank.CollectPart(v131);
									return;
								end;
							else
								functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
								return;
							end;
						end;
					end;
				elseif (l__mouse__26.Target.Position - u7.Position).magnitude <= 15 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
					v131 = nil;
					if l__mouse__26.Target:FindFirstChild("Pickup") then
						v131 = l__mouse__26.Target;
					elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
						v131 = l__mouse__26.Target.Parent;
					end;
					if v131 ~= nil then
						if functionBank.CanBearLoad(v131.Name) then
							l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
							l__ReplicatedStorage__2.Events.Pickup:FireServer(v131);
							if ping <= 0.001 then
								return;
							else
								functionBank.CollectPart(v131);
								return;
							end;
						else
							functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
							return;
						end;
					end;
				end;
			end;
		elseif u8 and os.clock() - u9 >= 0.25 and l__mouse__26.Target then
			if not l__mouse__26.Target:FindFirstChild("Pickup") then
				if l__mouse__26.Target.Parent:FindFirstChild("Pickup") and (l__mouse__26.Target.Position - u7.Position).magnitude <= 15 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
					local v132 = nil;
					if l__mouse__26.Target:FindFirstChild("Pickup") then
						v132 = l__mouse__26.Target;
					elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
						v132 = l__mouse__26.Target.Parent;
					end;
					if v132 ~= nil then
						if functionBank.CanBearLoad(v132.Name) then
							l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
							l__ReplicatedStorage__2.Events.Pickup:FireServer(v132);
							if ping <= 0.001 then
								return;
							else
								functionBank.CollectPart(v132);
								return;
							end;
						else
							functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
						end;
					end;
				end;
			elseif (l__mouse__26.Target.Position - u7.Position).magnitude <= 15 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
				v132 = nil;
				if l__mouse__26.Target:FindFirstChild("Pickup") then
					v132 = l__mouse__26.Target;
				elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
					v132 = l__mouse__26.Target.Parent;
				end;
				if v132 ~= nil then
					if functionBank.CanBearLoad(v132.Name) then
						l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
						l__ReplicatedStorage__2.Events.Pickup:FireServer(v132);
						if ping <= 0.001 then
							return;
						else
							functionBank.CollectPart(v132);
							return;
						end;
					else
						functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
					end;
				end;
			end;
		end;
	end;
end);
l__ReplicatedStorage__2.Events.CreateProjectile.OnClientEvent:connect(function(p36)
	MakeProjectile(p36.toolName, p36.originCF, p36.drawStrength, p36.owner);
end);
function MakeProjectile(p37, p38, p39, p40)
	local l__projectileName__133 = v20[p37].projectileName;
	local v134 = l__ReplicatedStorage__2.Projectiles:FindFirstChild(l__projectileName__133):Clone();
	v134.CFrame = p38;
	local v135 = {
		origin = p38.p, 
		position = p38.p, 
		velocity = p38.lookVector * math.clamp(v20[p37].velocityMagnitude * p39, 100, 500), 
		acceleration = Vector3.new(0, -156.2, 0), 
		age = os.time(), 
		toolFrom = p37, 
		object = v134
	};
	if 50 < (l__mouse__26.hit.p - u7.Position).magnitude then
		v135.velocity = v135.velocity + Vector3.new(0, 15, 0);
	end;
	v135.owned = p40 and false;
	print(v20[l__projectileName__133].velocityMagnitude, p39);
	u4[#u4 + 1] = v135;
	v134.Parent = workspace;
	if p40 then
		l__ReplicatedStorage__2.Events.CreateProjectile:FireServer({
			originCF = p38, 
			drawStrength = p39, 
			toolName = p37
		});
	end;
end;
local l__Gift__136 = l__MainGui__30.RightPanel.Shop.Gift;
_G.gift = false;
function UpdateText()
	local l__next__137 = next;
	local v138, v139 = l__MainGui__30.RightPanel.Shop.List:GetChildren();
	while true do
		local v140, v141 = l__next__137(v138, v139);
		if v140 then

		else
			break;
		end;
		v139 = v140;
		if v141:IsA("Frame") then
			if _G.gift == true then
				v141.OpenButton.Text = "BUY (GIFT)";
			else
				v141.OpenButton.Text = "BUY";
			end;
		end;	
	end;
end;
local u10 = false;
l__Gift__136.Activated:Connect(function()
	if not u10 then
		u10 = true;
		if _G.gift == true then
			_G.gift = false;
			l__Gift__136.Text = "GIFT PLAYER";
			UpdateText();
			l__ReplicatedStorage__2.Events.ChangePlr:FireServer();
		else
			_G.gift = true;
			l__Gift__136.Text = "DISABLE GIFT PLAYER";
			UpdateText();
		end;
		task.wait(0.5);
		u10 = false;
	end;
end);
_G.ID = 0;
local l__next__142 = next;
local v143, v144 = l__MainGui__30.RightPanel.Shop.List:GetChildren();
while true do
	local v145, v146 = l__next__142(v143, v144);
	if not v145 then
		break;
	end;
	v144 = v145;
	if v146:IsA("Frame") then
		v146.OpenButton.InputBegan:connect(function(p41, p42)
			if functionBank.InteractInput(p41, p42) then
				if _G.gift ~= true then
					l__MarketplaceService__8:PromptProductPurchase(l__LocalPlayer__25, v146.OpenButton.ProductId.Value);
					return;
				end;
			else
				return;
			end;
			l__MainGui__30.RightPanel.Scrolling.Visible = true;
			l__MainGui__30.LeftPanel.Shop.Visible = false;
			l__MainGui__30.LeftPanel.CodesLeft.Visible = false;
			l__MainGui__30.RightPanel.Shop.Visible = false;
			l__MainGui__30.RightPanel.Scrolling.TextLabel.Text = "Choose Player To Gift *" .. v146["Gold Title"].Text .. " coins*";
			_G.ID = v146.OpenButton.ProductId.Value;
		end);
	end;
end;
local v147 = {};
function v147.ChangeSkybox(p43)
	local l__next__148 = next;
	local v149, v150 = l__Lighting__7:GetChildren();
	while true do
		local v151, v152 = l__next__148(v149, v150);
		if not v151 then
			break;
		end;
		v150 = v151;
		if v152:IsA("Sky") then
			v152:Destroy();
		end;	
	end;
	l__ReplicatedStorage__2.Skies:FindFirstChild(p43):Clone().Parent = l__Lighting__7;
end;
function v147.DoomWeather()
	functionBank.ChangeSkybox("Doom");
	l__Lighting__7.FogEnd = v24.doomSuite.fogDist;
	l__Lighting__7.FogColor = v24.doomSuite.fogColor;
	l__Lighting__7.Brightness = v24.doomSuite.brightness;
end;
function v147.SunnyDays()
	functionBank.ChangeSkybox("Shine");
	l__Lighting__7.FogEnd = v24.shineSuite.fogDist;
	l__Lighting__7.FogColor = v24.shineSuite.fogColor;
	l__Lighting__7.Brightness = v24.shineSuite.brightness;
end;
local u11 = nil;
function v147.MakeItRain(p44)
	if not p44 then
		local l__next__153 = next;
		local v154, v155 = workspace:GetChildren();
		while true do
			local v156, v157 = l__next__153(v154, v155);
			if not v156 then
				break;
			end;
			v155 = v156;
			if v157.Name == "RainPart" then
				v157:Destroy();
			end;		
		end;
		l__ReplicatedStorage__2.LocalSounds.Nature.Rain:Stop();
		l__ReplicatedStorage__2.LocalSounds.Nature.Thunder:Stop();
		return;
	end;
	u11 = l__ReplicatedStorage__2.Misc.RainPart:Clone();
	u11.Parent = workspace;
	l__ReplicatedStorage__2.LocalSounds.Nature.Rain:Play();
	l__ReplicatedStorage__2.LocalSounds.Nature.Thunder:Play();
	functionBank.ChangeSkybox("Rain");
	l__Lighting__7.FogEnd = v24.rainSuite.fogDist;
	l__Lighting__7.FogColor = v24.rainSuite.fogColor;
	l__Lighting__7.Brightness = v24.rainSuite.brightness;
end;
function v147.RestorePhysicality(p45)
	if p45:IsA("BasePart") then
		p45.Anchored = false;
		p45.CanCollide = true;
		return;
	end;
	if p45:IsA("Model") then
		local l__next__158 = next;
		local v159, v160 = p45:GetDescendants();
		while true do
			local v161, v162 = l__next__158(v159, v160);
			if not v161 then
				break;
			end;
			v160 = v161;
			if v162:IsA("BasePart") then
				v162.Anchored = false;
				v162.CanCollide = true;
			end;		
		end;
	end;
end;
local u12 = nil;
local u13 = nil;
function v147.CursorRay(p46)
	local v163 = u12:ScreenPointToRay(l__mouse__26.x, l__mouse__26.y);
	local v164, v165, v166, v167 = workspace:FindPartOnRay(Ray.new(v163.Origin, v163.Direction * 250), p46 or u13);
	return v164, v165, v166, v167;
end;
function v147.MiddleScreenRay(p47)
	local v168 = u12:ScreenPointToRay(u12.ViewportSize.X / 2, u12.ViewportSize.Y / 2);
	local v169, v170, v171, v172 = workspace:FindPartOnRay(Ray.new(v168.Origin, v168.Direction * 9999), p47 or workspace);
	return v169, v170, v171, v172;
end;
function v147.FirstPartOnRay(p48, p49)
	local v173, v174, v175, v176 = workspace:FindPartOnRay(p48, p49);
	return v173, v174, v175, v176;
end;
function v147.UpdateBoosts()
	local l__next__177 = next;
	local v178, v179 = l__MainGui__30.LeftPanel.Shop.Lists.BoostList:GetChildren();
	while true do
		local v180, v181 = l__next__177(v178, v179);
		if not v180 then
			break;
		end;
		v179 = v180;
		if v181:IsA("Frame") then
			v181:Destroy();
		end;	
	end;
	for v182, v183 in next, v20 do
		if v183.fruit then
			local v184 = l__MainGui__30.LeftPanel.Shop.Templates.MarketFrame:Clone();
			if v183.cost then
				v184.TextButton.Text = v183.cost;
			end;
			v184.ImageButton.Image = v183.image and "";
			v184.AmountGiven.Text = v183.amount .. " " .. v182;
			v184.ItemNameLabel.Text = v182;
			v184.TextButton.Text = v183.cost .. " Gold";
			v184.LayoutOrder = v183.shopOrder;
			v184.Visible = true;
			v184.Parent = l__MainGui__30.LeftPanel.Shop.Lists.BoostList;
			v184.ImageButton.InputBegan:connect(function(p50, p51)
				if functionBank.InteractInput(p50, p51) then
					l__ReplicatedStorage__2.Events.PurchaseFromShop:FireServer(v182);
				end;
			end);
			v184.TextButton.InputBegan:connect(function(p52, p53)
				if functionBank.InteractInput(p52, p53) then
					l__ReplicatedStorage__2.Events.PurchaseFromShop:FireServer(v182);
				end;
			end);
		end;
	end;
	local v185 = l__MainGui__30.LeftPanel.Shop.Lists.BoostList:FindFirstChildOfClass("Frame");
	if v185 then
		local v186 = v185.AbsoluteSize.Y + 20;
	else
		v186 = 5;
	end;
	l__MainGui__30.LeftPanel.Shop.Lists.BoostList.CanvasSize = UDim2.new(1, 0, 0, #l__MainGui__30.LeftPanel.Shop.Lists.BoostList:GetChildren() * v186);
end;
function v147.UpdateGPList()
	local l__next__187 = next;
	local v188, v189 = l__MainGui__30.LeftPanel.Shop.Lists.GPList:GetChildren();
	while true do
		local v190, v191 = l__next__187(v188, v189);
		if not v190 then
			break;
		end;
		v189 = v190;
		if v191:IsA("Frame") then
			v191:Destroy();
		end;	
	end;
	for v192, v193 in next, v21 do
		if v193.ID then
			local v194 = l__MainGui__30.LeftPanel.Shop.Templates.GamepassFrame:Clone();
			local v195 = game:GetService("MarketplaceService"):GetProductInfo(v193.ID, v193.info);
			v194["Gold Title"].Text = v192;
			v194.Chests.Image = "rbxassetid://" .. v195.IconImageAssetId;
			v194.Title.Text = v195.PriceInRobux .. " R$";
			v194.LayoutOrder = v193.gpOrder;
			v194.Visible = true;
			v194.Parent = l__MainGui__30.LeftPanel.Shop.Lists.GPList;
			if l__MarketplaceService__8:UserOwnsGamePassAsync(l__LocalPlayer__25.UserId, v193.ID) then
				v194.OpenButton.Text = "OWNED";
			else
				v194.OpenButton.Text = "BUY";
			end;
			v194.OpenButton.InputBegan:connect(function(p54, p55)
				if functionBank.InteractInput(p54, p55) then
					if not l__MarketplaceService__8:UserOwnsGamePassAsync(l__LocalPlayer__25.UserId, v193.ID) then
						l__MarketplaceService__8:PromptGamePassPurchase(l__LocalPlayer__25, v193.ID);
						return;
					end;
				else
					return;
				end;
				return print("YOU OWN THIS...");
			end);
		end;
	end;
	local v196 = l__MainGui__30.LeftPanel.Shop.Lists.GPList:FindFirstChildOfClass("Frame");
	if v196 then
		local v197 = v196.AbsoluteSize.Y + 20;
	else
		v197 = 5;
	end;
	l__MainGui__30.LeftPanel.Shop.Lists.GPList.CanvasSize = UDim2.new(1, 0, 0, #l__MainGui__30.LeftPanel.Shop.Lists.GPList:GetChildren() * v197);
end;
function v147.UpdateCosmetics()
	local l__next__198 = next;
	local v199, v200 = l__MainGui__30.LeftPanel.Shop.Lists.CosmeticList:GetChildren();
	while true do
		local v201, v202 = l__next__198(v199, v200);
		if not v201 then
			break;
		end;
		v200 = v201;
		if v202:IsA("Frame") then
			v202:Destroy();
		end;	
	end;
	for v203, v204 in next, v20 do
		local v205 = false;
		if v204.cosmetic then
			local v206 = l__MainGui__30.LeftPanel.Shop.Templates.CosmeticFrame:Clone();
			if v204.cost then
				v206.TextButton.Text = v204.cost;
			else
				v206.TextButton.Text = "Event Item";
			end;
			v206.ImageButton.Image = v204.image and "";
			v206.ItemNameLabel.Text = v203;
			if _G.data.ownedCosmetics[v203] then
				if _G.data.appearance[v204.locus] ~= v203 then
					v206.TextButton.BackgroundColor3 = v19.goodGreen;
					v206.ItemNameLabel.TextColor3 = v19.goodGreen;
					v206.TextButton.Text = "WEAR";
				else
					v206.ItemNameLabel.TextColor3 = v19.badRed;
					v206.TextButton.BackgroundColor3 = v19.badRed;
					v206.TextButton.Text = "TAKE OFF";
				end;
				if v204.hiddenfromNonOwners == true then
					v206.ImageButton.BackgroundColor3 = Color3.fromRGB(137, 207, 240);
					v206.ImageButton.BackgroundTransparency = 0.5;
					v206.background.Image = "rbxassetid://10937422176";
					v206.ItemNameLabel.BackgroundColor3 = Color3.fromRGB(137, 207, 240);
					v206.ItemNameLabel.TextColor3 = Color3.fromRGB(92, 141, 163);
				end;
			elseif v204.hiddenfromNonOwners == true then
				print("hide!");
				v205 = true;
				v206.Visible = false;
			end;
			v206.LayoutOrder = v204.shopOrder;
			if v205 == false then
				v206.Visible = true;
			end;
			v206.Parent = l__MainGui__30.LeftPanel.Shop.Lists.CosmeticList;
			v206.ImageButton.InputBegan:connect(function(p56, p57)
				if functionBank.InteractInput(p56, p57) then
					if not _G.data.ownedCosmetics[v203] then
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.LastSelected.Value = v203;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ItemNameLabel.Text = string.upper(v203);
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.MojoCost.Text = "COST: " .. v204.cost;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ImageLabel.Image = v204.image;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Visible = true;
						return;
					end;
				else
					return;
				end;
				l__ReplicatedStorage__2.Events.EquipCosmetic:FireServer(v203);
			end);
			v206.TextButton.InputBegan:connect(function(p58, p59)
				if functionBank.InteractInput(p58, p59) then
					if not _G.data.ownedCosmetics[v203] then
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.LastSelected.Value = v203;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ItemNameLabel.Text = string.upper(v203);
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.MojoCost.Text = "COST: " .. v204.cost;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Backdrop.ImageLabel.Image = v204.image;
						l__MainGui__30.Panels.ConfirmPurchaseYe.Visible = true;
						return;
					end;
				else
					return;
				end;
				l__ReplicatedStorage__2.Events.EquipCosmetic:FireServer(v203);
				print("asking for equip");
			end);
		end;
	end;
	local v207 = l__MainGui__30.LeftPanel.Shop.Lists.CosmeticList:FindFirstChildOfClass("Frame");
	if v207 then
		local v208 = v207.AbsoluteSize.Y + 20;
	else
		v208 = 5;
	end;
	l__MainGui__30.LeftPanel.Shop.Lists.CosmeticList.CanvasSize = UDim2.new(1, 0, 0, #l__MainGui__30.LeftPanel.Shop.Lists.CosmeticList:GetChildren() * v208);
end;
function v147.NearestTotemAndDistance(p60)
	local v209 = nil;
	local v210, v211 = functionBank.IsInTribe();
	if v211 then
		v209 = v211.color;
	end;
	local v212 = nil;
	local v213 = math.huge;
	local l__next__214 = next;
	local v215, v216 = workspace.Totems:GetChildren();
	while true do
		local v217, v218 = l__next__214(v215, v216);
		if not v217 then
			break;
		end;
		v216 = v217;
		if v218.TribeColor.Value ~= v209 then
			local l__magnitude__219 = (v218.PrimaryPart.Position - p60).magnitude;
			if l__magnitude__219 < v213 then
				v212 = v218;
				v213 = l__magnitude__219;
			end;
		end;	
	end;
	return v212, v213;
end;
local u14 = nil;
function v147.ClearMouseBoundStructure()
	if u14 then
		u14:Destroy();
	end;
	u14 = nil;
	l__MainGui__30.Mobile.StructureButton.Visible = false;
end;
local u15 = 0;
function v147.BindMouseStructure(p61)
	functionBank.ClearMouseBoundStructure();
	if l__UserInputService__3.TouchEnabled then
		l__MainGui__30.Mobile.StructureButton.Visible = true;
	end;
	u14 = p61;
	local l__next__220 = next;
	local v221, v222 = u14:GetDescendants();
	while true do
		local v223, v224 = l__next__220(v221, v222);
		if not v223 then
			break;
		end;
		v222 = v223;
		if v224:IsA("BasePart") then
			if v224.Name == "Reference" or v224.Name == "Interactable" or v224.Name == "Effect" or v224.Name == "Portal" then
				v224.Transparency = 1;
			else
				v224.Transparency = 0.3;
			end;
			v224.Material = Enum.Material.Glass;
			v224.CanCollide = false;
			v224.Anchored = true;
		elseif not v224:IsA("Weld") and not v224:IsA("ManualWeld") then
			v224:Destroy();
		end;	
	end;
	local function v225(p62)
		if p62 then
			if u14.PrimaryPart.Color == v19.goodGreen then
				return;
			else
				local l__next__226 = next;
				local v227, v228 = u14:GetDescendants();
				while true do
					local v229, v230 = l__next__226(v227, v228);
					if not v229 then
						break;
					end;
					v228 = v229;
					if v230:IsA("BasePart") then
						v230.Color = v19.goodGreen;
					end;				
				end;
				return;
			end;
		end;
		if u14.PrimaryPart.BrickColor == v19.badRed then
			return;
		end;
		local l__next__231 = next;
		local v232, v233 = u14:GetDescendants();
		while true do
			local v234, v235 = l__next__231(v232, v233);
			if not v234 then
				break;
			end;
			v233 = v234;
			if v235:IsA("BasePart") then
				v235.Color = v19.badRed;
			end;		
		end;
	end;
	u14.Parent = u13;
	while u14 do
		l__mouse__26.TargetFilter = u14;
		local v236 = nil;
		local v237 = nil;
		local v238 = nil;
		if l__UserInputService__3.TouchEnabled then
			local v239, v240, v241, v242 = functionBank.RayUntil((u7.CFrame * CFrame.new(0, 10, -10 - u14:GetExtentsSize().Z / 2)).p, Vector3.new(0, -1000, 0));
			v236 = v239;
			v237 = v240;
			v238 = v242;
			u14:SetPrimaryPartCFrame(CFrame.new(v237, Vector3.new(u7.Position.X, v237.Y, u7.Position.Z)));
		elseif l__UserInputService__3.MouseEnabled then
			local v243, v244, v245, v246 = functionBank.RayUntil(l__mouse__26.Hit.p + Vector3.new(0, 10, 0), Vector3.new(0, -1000, 0));
			v236 = v243;
			v237 = v244;
			v238 = v246;
			u14:SetPrimaryPartCFrame(CFrame.new(v237) * CFrame.Angles(0, math.rad(u15), 0));
		end;
		local v247 = true;
		local v248, v249, v250 = pairs(workspace.Deployables:GetChildren());
		while true do
			local v251, v252 = v248(v249, v250);
			if not v251 then
				break;
			end;
			local v253 = v252:FindFirstChild("Reference") or v252:FindFirstChild("MainPart");
			if v253 then
				local l__magnitude__254 = (v253.Position - v237).magnitude;
				if u14.Name == "Chest" then
					if l__magnitude__254 <= 2 then
						v247 = false;
					end;
				else
					if v253.Name == "MainPart" then
						local v255 = 15;
					else
						v255 = 6;
					end;
					if l__magnitude__254 <= v255 then
						v247 = false;
					end;
				end;
			end;		
		end;
		local l__next__256 = next;
		local v257, v258 = game.Players:GetPlayers();
		while true do
			local v259, v260 = l__next__256(v257, v258);
			if not v259 then
				break;
			end;
			v258 = v259;
			if v260.Character and v260 ~= l__LocalPlayer__25 then
				if u14.Name == "Iron Turret" then
					local v261 = 23;
				else
					v261 = 8;
				end;
				if (v237 - v260.Character.PrimaryPart.Position).magnitude < v261 then
					v247 = false;
				end;
			end;		
		end;
		if (v237 - u7.Position).magnitude > 50 then
			v247 = false;
		end;
		if v236 ~= workspace.Terrain and v20[u14.Name].placement ~= "all" then
			v247 = false;
		end;
		if v238 and v238 == Enum.Material.Water and v20[u14.Name].placement ~= "sea" and v20[u14.Name].placement ~= "all" then
			v247 = false;
		end;
		if v238 and v238 ~= Enum.Material.Water and v20[u14.Name].placement == "sea" then
			v247 = false;
		end;
		if v20[u14.Name].recipe and not functionBank.CanCraftItem(u14.Name) then
			v247 = false;
		end;
		for v262, v263 in next, v12 do
			if v20[u14.Name].placement ~= "sea" and (v237 - v263.p).magnitude < 25 then
				v247 = false;
			end;
		end;
		local v264, v265 = functionBank.NearestTotemAndDistance(v237);
		if v265 < 175 then
			v247 = false;
		end;
		v225(v247);
		l__RunService__1.RenderStepped:wait();	
	end;
end;
function v147.IsInTribe()
	for v266, v267 in next, tribes do
		if v267.chief == l__LocalPlayer__25.Name then
			return v266, v267;
		end;
		for v268, v269 in next, v267.members do
			if v269 == l__LocalPlayer__25.Name then
				return v266, v267;
			end;
		end;
	end;
	return nil;
end;
function v147.UpdateGP(p63)
	local l__next__270 = next;
	local v271, v272 = l__MainGui__30.RightPanel.Scrolling.List:GetChildren();
	while true do
		local v273, v274 = l__next__270(v271, v272);
		if not v273 then
			break;
		end;
		v272 = v273;
		if v274:IsA("Frame") then
			v274:Destroy();
		end;	
	end;
	for v275, v276 in next, p63 do
		local v277 = l__MainGui__30.RightPanel.Scrolling.change.Plr:Clone();
		v277.Name = v276.playerName;
		v277.TextButton.Text = v276.playerName;
		v277.ImageLabel.Image = "https://www.roblox.com/headshot-thumbnail/image?userId=" .. v276.playerID .. "&width=420&height=420&format=png";
		v277.Parent = l__MainGui__30.RightPanel.Scrolling.List;
		v277.Visible = true;
		v277.TextButton.Activated:Connect(function()
			l__ReplicatedStorage__2.Events.ChangePlr:FireServer(v276.playerInstance);
			l__MarketplaceService__8:PromptProductPurchase(l__LocalPlayer__25, _G.ID);
		end);
		if v277.Name == l__LocalPlayer__25.Name then
			v277:Destroy();
		end;
	end;
end;
function v147.UpdatePlayerList(p64, p65)
	if l__UserInputService__3.TouchEnabled then
		l__SecondaryGui__31.UIScale.Scale = 0.6;
		l__MainGui__30.Panels.Card.UIScale.Scale = 0.75;
	elseif l__UserInputService__3.MouseEnabled then
		l__SecondaryGui__31.UIScale.Scale = 1;
		l__MainGui__30.Panels.Card.UIScale.Scale = 0.75;
	end;
	local l__next__278 = next;
	local v279, v280 = l__SecondaryGui__31.PlayerList.List:GetChildren();
	while true do
		local v281, v282 = l__next__278(v279, v280);
		if not v281 then
			break;
		end;
		v280 = v281;
		if v282:IsA("ImageButton") and v282.Name ~= "ActionPanel" then
			v282:Destroy();
		end;	
	end;
	local l__next__283 = next;
	local v284 = nil;
	while true do
		local v285, v286 = l__next__283(p64, v284);
		if not v285 then
			break;
		end;
		local v287 = l__SecondaryGui__31.PlayerList.Templates.PlayerTag:Clone();
		v287.Name = v286.playerName;
		v287.NameLabel.Text = v286.playerName;
		v287.TribeIcon.ImageColor3 = v286.playerColor;
		local v288 = nil;
		for v289, v290 in next, v19.TribeColors do
			if v290 == v286.playerColor then
				v288 = v289;
			end;
		end;
		v287.LevelLabel.Text = v286.playerLevel;
		v287.LayoutOrder = (v19.TribeOffsets[v288] and 0) + string.byte(string.sub(v286.playerName, 1, 1));
		v287.Parent = l__SecondaryGui__31.PlayerList.List;
		v287.Visible = true;
		v287.InputBegan:connect(function(p66, p67)
			if functionBank.InteractInput(p66, p67) then
				local v291 = "none";
				for v292, v293 in next, p65 do
					local v294 = nil;
					for v295, v296 in next, v293.members do
						if v296 == l__LocalPlayer__25.Name then
							v294 = true;
						end;
					end;
					if v294 then
						v291 = "member";
						break;
					end;
					if v293.chief == l__LocalPlayer__25.Name then
						v291 = "chief";
						break;
					end;
					v291 = "none";
				end;
				l__SecondaryGui__31.PlayerList.List.ActionPanel.KickButton.Visible = false;
				l__SecondaryGui__31.PlayerList.List.ActionPanel.InviteButton.Visible = false;
				if v291 == "chief" then
					l__SecondaryGui__31.PlayerList.List.ActionPanel.KickButton.Visible = true;
				end;
				if v291 == "chief" or v291 == "member" then
					l__SecondaryGui__31.PlayerList.List.ActionPanel.InviteButton.Visible = true;
				end;
				l__SecondaryGui__31.PlayerList.List.ActionPanel.Visible = true;
				l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value = v287.Name;
				l__SecondaryGui__31.PlayerList.List.ActionPanel.LayoutOrder = v287.LayoutOrder + 1;
			end;
		end);
		if l__SecondaryGui__31.PlayerList.List.ActionPanel.Visible and l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value and l__SecondaryGui__31.PlayerList.List:FindFirstChild(l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value) then
			l__SecondaryGui__31.PlayerList.List.ActionPanel.LayoutOrder = l__SecondaryGui__31.PlayerList.List:FindFirstChild(l__SecondaryGui__31.PlayerList.List.ActionPanel.TargetPlayerName.Value).LayoutOrder + 1;
		end;	
	end;
	l__SecondaryGui__31.PlayerList.List.CanvasSize = UDim2.new(0, 0, 0, #l__SecondaryGui__31.PlayerList.List:GetChildren() * 24);
end;
function v147.UpdateArmor()
	for v297, v298 in next, _G.data.armor do
		if v298 and v298 ~= "none" then
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].Image = v20[v298].image;
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].ActiveIcon.Visible = true;
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].DefaultIcon.Visible = false;
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].EmptyFrame.Visible = false;
		else
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].Image = "";
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].DefaultIcon.Visible = true;
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].EmptyFrame.Visible = true;
			l__MainGui__30.RightPanel.Inventory.ArmorFrame.Selection[v297].ActiveIcon.Visible = false;
		end;
	end;
end;
local u16 = 0;
local u17 = 0;
local u18 = 1;
function v147.MakeToast(p68)
	local l__message__299 = p68.message;
	local l__color__300 = p68.color;
	local l__duration__301 = p68.duration;
	if l__ReplicatedStorage__2.RelativeTime.Value - u16 < u17 then
		while true do
			wait(math.random() / 30);
			if u17 <= l__ReplicatedStorage__2.RelativeTime.Value - u16 then
				break;
			end;		
		end;
	end;
	u16 = l__ReplicatedStorage__2.RelativeTime.Value;
	u17 = l__duration__301 + 2;
	u18 = u18 + 1;
	local l__Toasts__302 = l__MainGui__30.Panels.Toasts;
	l__Toasts__302.Message.Text = "";
	l__Toasts__302.Title.Text = p68.title;
	l__Toasts__302.ImageLabel.Image = p68.image;
	l__Toasts__302.ImageLabel.BackgroundColor3 = l__color__300;
	l__Toasts__302.Message.TextColor3 = l__color__300;
	l__Toasts__302:TweenPosition(UDim2.new(1, 0, 0.75, 0), Enum.EasingDirection.In, Enum.EasingStyle.Quad, 1, true);
	wait(1);
	for v303 = 1, #l__message__299 do
		l__Toasts__302.Message.Text = string.sub(l__message__299, 1, v303);
		l__ReplicatedStorage__2.LocalSounds.Quicks.Text:Play();
		wait(0.04);
	end;
	wait(l__duration__301);
	if u18 == u18 then
		l__Toasts__302:TweenPosition(UDim2.new(1.5, 0, 0.75, 0), Enum.EasingDirection.Out, Enum.EasingStyle.Quad, 1, true);
	end;
end;
local u19 = {};
function v147.RayUntil(p69, p70)
	local v304, v305, v306, v307 = workspace:FindPartOnRayWithIgnoreList(Ray.new(p69, p70), u19);
	if not v304 or v304 == workspace.Terrain then
		u19 = {};
		return v304, v305, v306, v307;
	end;
	table.insert(u19, v304);
	return functionBank.RayUntil(p69, p70);
end;
function v147.CreateParticles(p71, p72, p73, p74, p75, p76)
	local v308 = Instance.new("Part");
	v308.Anchored = true;
	v308.CanCollide = false;
	v308.Transparency = 1;
	v308.Size = Vector3.new(0, 0, 0);
	v308.CFrame = CFrame.new(p72, p73);
	local v309 = p71:Clone();
	v309.Parent = v308;
	v309.EmissionDirection = Enum.NormalId.Front;
	if p76 then
		for v310, v311 in next, p76 do
			v309[v310] = v311;
		end;
	end;
	v308.Parent = workspace;
	wait();
	if not p74 then
		l__Debris__5:AddItem(v308, p75);
		return;
	end;
	v309.Rate = 0;
	v309:Emit(p74);
	l__Debris__5:AddItem(v308, p75);
end;
function v147.CollectPart(p77)
	if not p77:IsA("BasePart") then
		p77:Destroy();
		return;
	end;
	local v312 = p77:Clone();
	v312:ClearAllChildren();
	v312.CanCollide = false;
	v312.Anchored = true;
	p77:Destroy();
	v312.Parent = u12;
	l__TweenService__6:Create(v312, TweenInfo.new(0.2, Enum.EasingStyle.Quad, Enum.EasingDirection.In, 0, false, 0), {
		CFrame = u7.CFrame, 
		Size = Vector3.new(0.6, 0.6, 0.6), 
		Transparency = 1
	}):Play();
	l__Debris__5:AddItem(v312, 0.2);
end;
function v147.CleanNils(p78)
	local v313 = {};
	for v314, v315 in next, p78 do
		v313[#v313 + 1] = v315;
	end;
	return v313;
end;
function v147.AppendTables(p79)
	local v316 = {};
	for v317, v318 in next, p79 do
		for v319, v320 in next, v318 do
			v316[#v316 + 1] = v320;
		end;
	end;
	return v316;
end;
function v147.DrawTribeGui()
	tribes = l__ReplicatedStorage__2.Events.RequestTribeData:InvokeServer();
	local v321, v322 = functionBank.IsInTribe();
	if v321 then
		l__MainGui__30.LeftPanel.Tribe.Chief.ImageLabel.BackgroundColor3 = v19.TribeColors[v322.color];
		l__MainGui__30.LeftPanel.Tribe.Chief.Message.TextColor3 = v19.TribeColors[v322.color];
		if v322.message ~= "" then
			l__MainGui__30.LeftPanel.Tribe.Chief.Message.Text = "\"" .. v322.message .. "\"";
		else
			l__MainGui__30.LeftPanel.Tribe.Chief.Message.Text = "";
		end;
		l__MainGui__30.LeftPanel.Tribe.Members.MembersTitle.Text = "MEMBERS";
		l__MainGui__30.LeftPanel.Tribe.Members.MembersTitle.BackgroundColor3 = v19.TribeColors[v322.color];
		l__MainGui__30.LeftPanel.Tribe.Title.Text = string.upper(v322.color) .. " TRIBE";
		l__MainGui__30.LeftPanel.Tribe.Title.TextColor3 = v19.TribeColors[v322.color];
		local l__next__323 = next;
		local v324, v325 = l__MainGui__30.LeftPanel.Tribe.Members.Frame.List:GetChildren();
		while true do
			local v326, v327 = l__next__323(v324, v325);
			if not v326 then
				break;
			end;
			v325 = v326;
			if v327:IsA("TextButton") then
				v327:Destroy();
			end;		
		end;
		local v328 = l__MainGui__30.LeftPanel.Tribe.Members.Frame.Templates.TextButton:Clone();
		v328.BackgroundColor3 = v19.TribeColors[v322.color];
		v328.Text = "Chief " .. v322.chief;
		v328.Parent = l__MainGui__30.LeftPanel.Tribe.Members.Frame.List;
		v328.Visible = true;
		for v329, v330 in next, v322.members do
			local v331 = l__MainGui__30.LeftPanel.Tribe.Members.Frame.Templates.TextButton:Clone();
			v331.Text = v330;
			v331.Parent = l__MainGui__30.LeftPanel.Tribe.Members.Frame.List;
			v331.Visible = true;
		end;
	end;
end;
function v147.CreateSound(p80, p81, p82)
	p80 = p80:Clone();
	p80.Parent = p81;
	if p82 then
		p80.Pitch = p80.Pitch + (p80.DefaultPitch.Value and 1) * (math.random(-25, 25) / 100);
	end;
	p80:Play();
	spawn(function()
		while true do
			if not (p80.TimeLength > 0) then
				wait();
			end;
			if p80.TimeLength > 0 then
				break;
			end;		
		end;
		l__Debris__5:AddItem(p80, p80.TimeLength);
	end);
end;
local u20 = 1;
function v147.CreateNotification(p83, p84, p85, p86)
	wait(p86 and 0);
	p85 = p85 and 1;
	if #l__MainGui__30.Subordinates.Notifications:GetChildren() - 2 >= 3 then
		local v332 = nil;
		local v333 = math.huge;
		local l__next__334 = next;
		local v335, v336 = l__MainGui__30.Subordinates.Notifications:GetChildren();
		while true do
			local v337, v338 = l__next__334(v335, v336);
			if not v337 then
				break;
			end;
			v336 = v337;
			if v338:IsA("TextLabel") and v338.LayoutOrder < v333 then
				v332 = v338;
				v333 = v338.LayoutOrder;
			end;		
		end;
		if v332 then
			v332:Destroy();
		end;
	end;
	local v339 = l__MainGui__30.Subordinates.Notifications.Templates.TextLabel:Clone();
	v339.Text = p83;
	v339.TextColor3 = p84 or Color3.fromRGB(255, 255, 255);
	v339.LayoutOrder = u20;
	u20 = u20 + 1;
	v339.Parent = l__MainGui__30.Subordinates.Notifications;
	v339.Visible = true;
	l__Debris__5:AddItem(v339, p85 + 2);
	l__TweenService__6:Create(v339, TweenInfo.new(2, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut, 0, false, p85 and 1), {
		BackgroundTransparency = 1, 
		TextTransparency = 1, 
		TextStrokeTransparency = 1
	}):Play();
end;
local u21 = nil;
function v147.UpdateBillboards(p87)
	if u21 then
		local v340 = l__PlayerGui__29:FindFirstChild(u21.Name);
		if not v340 then
			return;
		end;
		if p87 then
			v340:Destroy();
			u21 = nil;
			return;
		end;
		local l__next__341 = next;
		local v342, v343 = v340.Frame.List:GetChildren();
		while true do
			local v344, v345 = l__next__341(v342, v343);
			if not v344 then
				break;
			end;
			v343 = v344;
			if v345:IsA("ImageButton") then
				v345:Destroy();
			end;		
		end;
		if v340.Name == "Campfire" then
			for v346, v347 in next, _G.data.inventory do
				if v20[v347.name].fuels then
					local v348 = v340.Frame.Templates.ImageButton:Clone();
					v348.Image = v20[v347.name].image;
					v348.TextLabel.Text = v347.quantity;
					v348.Name = v347.name;
					v348.Parent = v340.Frame.List;
					v348.Visible = true;
					v348.MouseButton1Down:connect(function()
						l__ReplicatedStorage__2.Events.lnteractStructure:FireServer(u21, v348.Name);
						l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
						u21.Board.Billboard.Backdrop.TextLabel.Text = math.floor(tonumber(u21.Board.Billboard.Backdrop.TextLabel.Text) + 0.5);
						u21.Board.Billboard.Backdrop.Slider.Size = UDim2.new(tonumber(u21.Board.Billboard.Backdrop.TextLabel.Text) / v20[u21.Name].capacity, 0, 1, 0);
						u21.Board.Billboard.Backdrop.Slider.BackgroundColor3 = Color3.fromRGB(255, 0, 0):lerp(Color3.fromRGB(170, 255, 0), u21.Board.Billboard.Backdrop.TextLabel.Text / 100);
						if not (v20[u21.Name].capacity * 0.95 <= tonumber(u21.Board.Billboard.Backdrop.TextLabel.Text)) then
							return;
						end;
						v340:Destroy();
						u21 = nil;
					end);
				end;
			end;
			return;
		end;
		if v340.Name == "Plant Box" then
			for v349, v350 in next, _G.data.inventory do
				if v20[v350.name] and v20[v350.name].grows then
					local v351 = v340.Frame.Templates.ImageButton:Clone();
					v351.Image = v20[v350.name].image;
					v351.TextLabel.Text = v350.quantity;
					v351.Name = v350.name;
					v351.Parent = v340.Frame.List;
					v351.Visible = true;
					v351.MouseButton1Down:connect(function()
						l__ReplicatedStorage__2.Events.lnteractStructure:FireServer(u21, v351.Name);
						l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
					end);
				end;
			end;
			return;
		end;
		if v340.Name == "Grinder" then
			for v352, v353 in next, _G.data.inventory do
				if v20[v353.name].grindsTo then
					local v354 = v340.Frame.Templates.ImageButton:Clone();
					v354.Image = v20[v353.name].image;
					v354.TextLabel.Text = v353.quantity;
					v354.Name = v353.name;
					v354.Parent = v340.Frame.List;
					v354.Visible = true;
					v354.MouseButton1Down:connect(function()
						l__ReplicatedStorage__2.Events.lnteractStructure:FireServer(u21, v354.Name);
						l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
					end);
				end;
			end;
			return;
		end;
		if v340.Name == "Coin Press" then
			for v355, v356 in next, _G.data.inventory do
				if v356.name == "Gold" then
					local v357 = v340.Frame.Templates.ImageButton:Clone();
					v357.Image = v20[v356.name].image;
					v357.TextLabel.Text = v356.quantity;
					v357.Name = v356.name;
					v357.Parent = v340.Frame.List;
					v357.Visible = true;
					v357.MouseButton1Down:connect(function()
						l__ReplicatedStorage__2.Events.lnteractStructure:FireServer(u21, v357.Name);
						l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
					end);
				end;
			end;
			return;
		end;
	end;
end;
local u22 = nil;
function v147.UpdateStats()
	l__MainGui__30.Panels.Stats.Food.Slider.Size = UDim2.new(_G.data.stats.food / 100, 0, 1, 0);
	if u22 then
		l__MainGui__30.Panels.Stats.Health.Slider.Size = UDim2.new(math.clamp(u22.Health / u22.MaxHealth, 0, 1), 0, 1, 0);
	end;
	if _G.data.spell then
		l__MainGui__30.Panels.Stats.Voodoo.Visible = true;
		l__MainGui__30.Panels.Stats.VoodooTitle.Visible = true;
		l__MainGui__30.Panels.Stats.Voodoo.Slider.Size = UDim2.new(math.clamp(_G.data.voodoo / 100, 0, 1), 0, 1, 0);
		l__MainGui__30.Panels.Stats.SpellImage.ImageButton.Image = v20[_G.data.spell].image;
		l__MainGui__30.Panels.Stats.SpellImage.Visible = true;
	else
		l__MainGui__30.Panels.Stats.Voodoo.Visible = false;
		l__MainGui__30.Panels.Stats.VoodooTitle.Visible = false;
		l__MainGui__30.Panels.Stats.SpellImage.Visible = false;
	end;
	local v358, v359 = functionBank.CalculateLoad();
	l__MainGui__30.Panels.Stats.Bag.Slider.Size = UDim2.new(math.clamp(v358 / v359, 0, 1), 0, 1, 0);
	l__MainGui__30.Panels.Topbar.EssenceText.Text = _G.data.essence;
	l__MainGui__30.Panels.Topbar.EssenceBar.TextLabel.Text = "lvl " .. _G.data.level;
	if l__UserInputService__3.TouchEnabled then
		l__MainGui__30.Panels.Topbar.EssenceBar.AnchorPoint = Vector2.new(1, 0);
		l__MainGui__30.Panels.Topbar.EssenceBar.Position = UDim2.new(1, 0, 0.5, 0);
		l__MainGui__30.Panels.Topbar.EssenceBar.Size = UDim2.new(0.2, 0, 0.35, 0);
	elseif l__UserInputService__3.MouseEnabled then
		l__MainGui__30.Panels.Topbar.EssenceBar.AnchorPoint = Vector2.new(0.5, 0.5);
		l__MainGui__30.Panels.Topbar.EssenceBar.Position = UDim2.new(0.5, 0, 0.5, 0);
		l__MainGui__30.Panels.Topbar.EssenceBar.Size = UDim2.new(0.25, 0, 0.5, 0);
	end;
	l__MainGui__30.Panels.Topbar.EssenceBar.Slider.Size = UDim2.new(_G.data.essence / (v22[_G.data.level] or math.huge), 0, 1, 0);
	if _G.data.level >= 100 then
		l__MainGui__30.LeftPanel.Mojo.Tip.Visible = false;
		l__MainGui__30.LeftPanel.Mojo.RebirthButton.Visible = true;
	else
		l__MainGui__30.LeftPanel.Mojo.Tip.Visible = true;
		l__MainGui__30.LeftPanel.Mojo.RebirthButton.Visible = false;
	end;
	l__MainGui__30.Panels.Topbar.CoinsText.Text = _G.data.coins;
	l__MainGui__30.Panels.Topbar.MojoText.Text = _G.data.mojo;
	if l__LocalPlayer__25.Character and (l__LocalPlayer__25.Character:FindFirstChild("HumanoidRootPart") and not l__LocalPlayer__25.Character.PrimaryPart.CanCollide) then
		l__LocalPlayer__25:Kick();
	end;
end;
function v147.HasItem(p88)
	for v360, v361 in next, _G.data.inventory do
		if v361.name == p88 then
			return v360;
		end;
	end;
	return false;
end;
function v147.RedeemCode()
	local l__CreateButton__362 = l__MainGui__30.LeftPanel.CodesLeft.Frame.CreateButton;
	local l__TextBox__363 = l__MainGui__30.LeftPanel.CodesLeft.Frame.Frame.Frame.TextBox;
	if l__TextBox__363.Text ~= "" or l__TextBox__363.Text == nil then
		local v364 = l__ReplicatedStorage__2.Events.RedeemCode:InvokeServer(l__TextBox__363.Text);
		if v364 == true then
			l__TextBox__363.Text = "";
			l__CreateButton__362.Text = "Code successfully redeemed!";
			wait(1);
			l__CreateButton__362.Text = "Redeem";
			return;
		end;
		if v364 == "Underaged" then
			l__TextBox__363.Text = "";
			l__CreateButton__362.Text = "Your account is not old enough!";
			wait(1);
			l__CreateButton__362.Text = "Redeem";
			return;
		end;
		if v364 == "Used" then
			l__TextBox__363.Text = "";
			l__CreateButton__362.Text = "Code already redeemed!";
			wait(1);
			l__CreateButton__362.Text = "Redeem";
			return;
		end;
		if v364 == "Expired" then
			l__TextBox__363.Text = "";
			l__CreateButton__362.Text = "Code Expired :(";
			wait(1);
			l__CreateButton__362.Text = "Redeem";
			return;
		end;
		if v364 == false then
			l__TextBox__363.Text = "";
			l__CreateButton__362.Text = "Invalid Code!";
			wait(1);
			l__CreateButton__362.Text = "Redeem";
		end;
	end;
end;
function v147.HasMojoRecipe(p89)
	return _G.data.mojoItems[p89];
end;
function v147.CanCraftItem(p90)
	local v365 = true;
	for v366, v367 in next, v20[p90].recipe do
		local v368 = functionBank.HasItem(v366);
		if v368 then
			if _G.data.inventory[v368].quantity < v367 then
				v365 = false;
			end;
		else
			v365 = false;
		end;
	end;
	return v365;
end;
function v147.CalculateLoad()
	local v369 = 0;
	if _G.data.armor.bag and _G.data.armor.bag ~= "none" then
		local v370 = v20[_G.data.armor.bag].maxLoad;
	else
		v370 = 50;
	end;
	for v371, v372 in next, _G.data.inventory do
		if v372.quantity and v20[v372.name] then
			v369 = v369 + v372.quantity * (v20[v372.name].load and 0);
		end;
	end;
	return v369, v370;
end;
function v147.CanBearLoad(p91)
	local v373 = v20[p91].load and 0;
	local v374, v375 = functionBank.CalculateLoad();
	if not (v374 + v373 <= v375) and v373 ~= 0 then
		return false;
	end;
	return true;
end;
function v147.OpenGui(p92)
	if not p92 then
		l__SecondaryGui__31.PlayerList.Visible = true;
		for v376, v377 in next, functionBank.AppendTables({ l__MainGui__30.RightPanel:GetChildren(), l__MainGui__30.LeftPanel:GetChildren() }) do
			if v377:IsA("Frame") then
				v377.Visible = false;
			end;
		end;
		local l__next__378 = next;
		local v379, v380 = l__MainGui__30.Panels.Card.List:GetChildren();
		while true do
			local v381, v382 = l__next__378(v379, v380);
			if not v381 then
				break;
			end;
			v380 = v381;
			if v382:IsA("Frame") then
				v382.ImageButton.BackgroundColor3 = v19.CardDefaultColors[v382.Name];
				v382.Status.Value = false;
				functionBank.ClearMouseBoundStructure();
			end;		
		end;
		return;
	end;
	functionBank.ClearMouseBoundStructure();
	if p92.Status.Value then
		l__SecondaryGui__31.PlayerList.Visible = true;
		l__PlayerGui__29.Chat.Frame.Visible = true;
		for v383, v384 in next, functionBank.AppendTables({ l__MainGui__30.RightPanel:GetChildren(), l__MainGui__30.LeftPanel:GetChildren() }) do
			if v384:IsA("Frame") then
				v384.Visible = false;
			end;
		end;
		local l__next__385 = next;
		local v386, v387 = l__MainGui__30.Panels.Card.List:GetChildren();
		while true do
			local v388, v389 = l__next__385(v386, v387);
			if not v388 then
				break;
			end;
			v387 = v388;
			if v389:IsA("Frame") then
				v389.ImageButton.BackgroundColor3 = v19.CardDefaultColors[v389.Name];
				v389.Status.Value = false;
			end;		
		end;
		return;
	end;
	for v390, v391 in next, functionBank.AppendTables({ l__MainGui__30.RightPanel:GetChildren(), l__MainGui__30.LeftPanel:GetChildren() }) do
		if v391:IsA("Frame") then
			v391.Visible = false;
		end;
	end;
	local l__next__392 = next;
	local v393, v394 = l__MainGui__30.Panels.Card.List:GetChildren();
	while true do
		local v395, v396 = l__next__392(v393, v394);
		if not v395 then
			break;
		end;
		v394 = v395;
		if v396:IsA("Frame") then
			v396.ImageButton.BackgroundColor3 = v19.CardDefaultColors[v396.Name];
			v396.Status.Value = false;
		end;	
	end;
	l__SecondaryGui__31.PlayerList.Visible = true;
	l__PlayerGui__29.Chat.Frame.Visible = true;
	local l__next__397 = next;
	local v398, v399 = p92.Opens:GetChildren();
	while true do
		local v400, v401 = l__next__397(v398, v399);
		if not v400 then
			break;
		end;
		v401.Value.Visible = true;
		if v401.Value:IsDescendantOf(l__MainGui__30.RightPanel) then
			l__SecondaryGui__31.PlayerList.Visible = false;
		end;
		if v401.Value:IsDescendantOf(l__MainGui__30.LeftPanel) and l__UserInputService__3.TouchEnabled then
			l__PlayerGui__29.Chat.Frame.Visible = false;
		end;
		if v401.Value == l__MainGui__30.LeftPanel.Tribe then
			local v402, v403 = functionBank.IsInTribe();
			if not v402 then
				print("not in a tribe ree");
				v401.Value.Visible = false;
				l__MainGui__30.LeftPanel.NewTribe.Visible = true;
				local l__next__404 = next;
				local v405, v406 = l__MainGui__30.LeftPanel.NewTribe.Frame.Frame.ColorList:GetChildren();
				while true do
					local v407, v408 = l__next__404(v405, v406);
					if not v407 then
						break;
					end;
					v406 = v407;
					if v408:IsA("ImageButton") then
						v408:Destroy();
					end;				
				end;
				for v409, v410 in next, v19.TribeColors do
					local v411 = l__MainGui__30.LeftPanel.NewTribe.Frame.Frame.Templates.ImageButton:Clone();
					for v412, v413 in next, tribes do
						if v413.color == v409 then
							local v414 = game.Players:FindFirstChild(v413.chief and "");
							if v414 then
								v411.Image = "https://web.roblox.com/Thumbs/Avatar.ashx?x=100&y=100&Format=Png&userid=" .. v414.UserId;
							end;
						end;
					end;
					v411.BackgroundColor3 = v410;
					v411.Visible = true;
					v411.Parent = l__MainGui__30.LeftPanel.NewTribe.Frame.Frame.ColorList;
					v411.InputBegan:connect(function(p93, p94)
						if functionBank.InteractInput(p93, p94) then
							u1 = v409;
							l__MainGui__30.LeftPanel.NewTribe.Frame.ColorTitle.BackgroundColor3 = v410;
							l__MainGui__30.LeftPanel.NewTribe.Frame.ColorTitle.TextColor3 = v410;
							l__MainGui__30.LeftPanel.NewTribe.Frame.ColorTitle.Text = string.upper(v409);
							local l__next__415 = next;
							local v416, v417 = l__MainGui__30.LeftPanel.NewTribe.Frame.Frame.ColorList:GetChildren();
							while true do
								local v418, v419 = l__next__415(v416, v417);
								if not v418 then
									break;
								end;
								v417 = v418;
								if v419:IsA("ImageButton") then
									if v419.BackgroundColor3 ~= v410 then
										v419.BorderSizePixel = 0;
									else
										v419.BorderSizePixel = 5;
									end;
								end;							
							end;
						end;
					end);
				end;
			end;
		end;	
	end;
	p92.ImageButton.BackgroundColor3 = v19.goodGreen;
	p92.Status.Value = true;
end;
function v147.PreQuantity(p95)
	for v420, v421 in next, _G.data.inventory do
		if v421.name == p95 and v421.quantity then
			return v421.quantity;
		end;
	end;
	return 0;
end;
function v147.InteractInput(p96, p97)
	if p97 then
		return;
	end;
	if p96.UserInputType ~= Enum.UserInputType.MouseButton1 and p96.UserInputType ~= Enum.UserInputType.Touch and p96.KeyCode ~= Enum.KeyCode.ButtonA then
		return false;
	end;
	return true;
end;
function v147.UpdateMojoMenu()
	local l__next__422 = next;
	local v423, v424 = l__MainGui__30.LeftPanel.Mojo.Lists.MojoList:GetChildren();
	while true do
		local v425, v426 = l__next__422(v423, v424);
		if not v425 then
			break;
		end;
		v424 = v425;
		if v426:IsA("Frame") and _G.data.mojoItems[v426.Name] then
			v426.ItemNameLabel.TextColor3 = v19.goodGreen;
			if v20[v426.Name].toggleable then
				v426.TextButton.Visible = true;
			else
				v426.TextButton.Visible = false;
			end;
			if _G.data.disabledMojo[v426.Name] then
				v426.TextButton.BackgroundColor3 = v19.goodGreen;
				v426.TextButton.Text = "TURN ON";
			else
				v426.TextButton.BackgroundColor3 = v19.badRed;
				v426.TextButton.Text = "TURN OFF";
			end;
		end;	
	end;
	local v427 = l__MainGui__30.LeftPanel.Mojo.Lists.MojoList:FindFirstChildOfClass("Frame");
	if v427 then
		local v428 = v427.AbsoluteSize.Y + 15;
	else
		v428 = 5;
	end;
	l__MainGui__30.LeftPanel.Mojo.Lists.MojoList.CanvasSize = UDim2.new(1, 0, 0, #l__MainGui__30.LeftPanel.Mojo.Lists.MojoList:GetChildren() * v428);
end;
function v147.UpdateCraftMenu()
	local l__next__429 = next;
	local v430, v431 = l__MainGui__30.LeftPanel.Craft.List:GetChildren();
	while true do
		local v432, v433 = l__next__429(v430, v431);
		if not v432 then
			break;
		end;
		v431 = v432;
		if v433:IsA("ImageLabel") and v433.Name ~= "LockedFrame" then
			local v434 = v20[v433.Name];
			local v435 = true;
			local l__next__436 = next;
			local l__recipe__437 = v20[v433.Name].recipe;
			local v438 = nil;
			while true do
				local v439 = nil;
				local v440, v441 = l__next__436(l__recipe__437, v438);
				if not v440 then
					break;
				end;
				v438 = v440;
				v439 = v433:FindFirstChild(v440);
				local v442 = functionBank.HasItem(v440);
				if v442 then
					if _G.data.inventory[v442].quantity < v441 then
						v435 = false;
						v439.Title.TextColor3 = v19.badRed;
					else
						v439.Title.TextColor3 = Color3.fromRGB(255, 255, 255);
					end;
				else
					v435 = false;
					v439.Title.TextColor3 = v19.badRed;
				end;			
			end;
			if v435 then
				v433.CraftButton.CanCraftImage.Visible = true;
				v433.CraftButton.NoCraftImage.Visible = false;
			else
				v433.CraftButton.CanCraftImage.Visible = false;
				v433.CraftButton.NoCraftImage.Visible = true;
			end;
		end;	
	end;
end;
local u23 = nil;
function v147.DrawCraftMenu(p98, p99)
	local l__next__443 = next;
	local v444, v445 = l__MainGui__30.LeftPanel.Craft.List:GetChildren();
	while true do
		local v446, v447 = l__next__443(v444, v445);
		if not v446 then
			break;
		end;
		v445 = v446;
		if v447:IsA("ImageLabel") then
			v447:Destroy();
		end;	
	end;
	local l__next__448 = next;
	local v449 = nil;
	while true do
		local v450, v451 = l__next__448(v20, v449);
		if not v450 then
			break;
		end;
		local v452 = true;
		if not v451.recipe then
			v452 = false;
		end;
		if p98 and p98 ~= "all" and v451.itemType ~= p98 then
			v452 = false;
		end;
		if p99 and not v450:lower():match(p99:lower()) then
			v452 = false;
		end;
		if v452 then
			if v451.mojoRecipe then
				if functionBank.HasMojoRecipe(v450) then
					local v453 = l__MainGui__30.LeftPanel.Craft.Templates.ItemFrame:Clone();
					v453.ItemIconBackdrop.ItemIcon.Image = v451.image;
					v453.NameLabel.Text = v450;
					v453.Name = v450;
					local v454 = true;
					local v455 = 0;
					for v456, v457 in next, v451.recipe do
						v455 = v455 + 1;
						local v458 = v453:FindFirstChild("Ingredient" .. v455);
						v458.ItemIcon.Image = v20[v456].image;
						v458.Title.Text = v457 .. " " .. v456;
						v458.Name = v456;
						v458.Visible = true;
						local v459 = functionBank.HasItem(v456);
						if v459 then
							if _G.data.inventory[v459].quantity and not (v457 <= _G.data.inventory[v459].quantity) then
								v458.ItemIcon.BackgroundColor3 = v19.badRed;
								v458.Title.TextColor3 = v19.badRed;
								v454 = false;
							end;
						else
							v458.ItemIcon.BackgroundColor3 = v19.badRed;
							v458.Title.TextColor3 = v19.badRed;
							v454 = false;
						end;
					end;
					if v454 then
						v453.CraftButton.CanCraftImage.Visible = true;
						v453.CraftButton.NoCraftImage.Visible = false;
					else
						v453.CraftButton.CanCraftImage.Visible = false;
						v453.CraftButton.NoCraftImage.Visible = true;
					end;
					v453.CraftButton.InputBegan:connect(function(p100, p101)
						if functionBank.InteractInput(p100, p101) and functionBank.CanCraftItem(v450) then
							l__ReplicatedStorage__2.LocalSounds.Quicks.Click1:Play();
							if not v451.deployable then
								l__ReplicatedStorage__2.Events.CraftItem:FireServer(v450);
								return;
							end;
						else
							return;
						end;
						functionBank.OpenGui();
						if u23 then
							u23 = nil;
						end;
						functionBank.BindMouseStructure(l__ReplicatedStorage__2.Deployables:FindFirstChild(v450):Clone());
					end);
					v453.LayoutOrder = 999;
					v453.Parent = l__MainGui__30.LeftPanel.Craft.List;
					v453.Visible = true;
				else
					local v460 = l__MainGui__30.LeftPanel.Craft.Templates.LockedFrame:Clone();
					v460.NameLabel.Text = "locked [MOJO]";
					v460.SecretTitle.Text = v450;
					v460.ItemIconBackdrop.ItemIcon.Image = v451.image;
					v460.LayoutOrder = 998;
					v460.Parent = l__MainGui__30.LeftPanel.Craft.List;
					v460.Visible = true;
				end;
			end;
			if v451.craftLevel <= _G.data.level and not v451.mojoRecipe then
				local v461 = l__MainGui__30.LeftPanel.Craft.Templates.ItemFrame:Clone();
				v461.ItemIconBackdrop.ItemIcon.Image = v451.image;
				v461.NameLabel.Text = v450;
				v461.Name = v450;
				local v462 = true;
				local v463 = 0;
				for v464, v465 in next, v451.recipe do
					v463 = v463 + 1;
					local v466 = v461:FindFirstChild("Ingredient" .. v463);
					v466.ItemIcon.Image = v20[v464].image;
					v466.Title.Text = v465 .. " " .. v464;
					v466.Name = v464;
					v466.Visible = true;
					local v467 = functionBank.HasItem(v464);
					if v467 then
						if _G.data.inventory[v467].quantity and not (v465 <= _G.data.inventory[v467].quantity) then
							v466.ItemIcon.BackgroundColor3 = v19.badRed;
							v466.Title.TextColor3 = v19.badRed;
							v462 = false;
						end;
					else
						v466.ItemIcon.BackgroundColor3 = v19.badRed;
						v466.Title.TextColor3 = v19.badRed;
						v462 = false;
					end;
				end;
				if v462 then
					v461.CraftButton.CanCraftImage.Visible = true;
					v461.CraftButton.NoCraftImage.Visible = false;
				else
					v461.CraftButton.CanCraftImage.Visible = false;
					v461.CraftButton.NoCraftImage.Visible = true;
				end;
				v461.CraftButton.InputBegan:connect(function(p102, p103)
					if functionBank.InteractInput(p102, p103) and functionBank.CanCraftItem(v450) then
						l__ReplicatedStorage__2.LocalSounds.Quicks.Click1:Play();
						if not v451.deployable then
							l__ReplicatedStorage__2.Events.CraftItem:FireServer(v450);
							return;
						end;
					else
						return;
					end;
					functionBank.OpenGui();
					if u23 then
						u23 = nil;
					end;
					functionBank.BindMouseStructure(l__ReplicatedStorage__2.Deployables:FindFirstChild(v450):Clone());
				end);
				v461.LayoutOrder = v451.craftLevel;
				v461.Parent = l__MainGui__30.LeftPanel.Craft.List;
				v461.Visible = true;
			elseif not v451.mojoRecipe then
				local v468 = l__MainGui__30.LeftPanel.Craft.Templates.LockedFrame:Clone();
				v468.NameLabel.Text = "locked [" .. v451.craftLevel .. "]";
				v468.SecretTitle.Text = v450;
				v468.ItemIconBackdrop.ItemIcon.Image = v451.image;
				v468.LayoutOrder = 200 + v451.craftLevel;
				v468.Parent = l__MainGui__30.LeftPanel.Craft.List;
				v468.Visible = true;
			end;
		end;	
	end;
	local v469 = l__MainGui__30.LeftPanel.Craft.List:FindFirstChildOfClass("ImageLabel");
	if v469 then
		local v470 = v469.AbsoluteSize.Y + 15;
	else
		v470 = 5;
	end;
	l__MainGui__30.LeftPanel.Craft.List.CanvasSize = UDim2.new(1, 0, 0, #l__MainGui__30.LeftPanel.Craft.List:GetChildren() * v470);
end;
local u24 = "all";
local u25 = nil;
function v147.DrawInventory(p104)
	if not p104 then
		p104 = u24;
	end;
	local l__next__471 = next;
	local v472, v473 = l__MainGui__30.LeftPanel.Shop.Lists.ChestList:GetChildren();
	while true do
		local v474, v475 = l__next__471(v472, v473);
		if not v474 then
			break;
		end;
		v473 = v474;
		if v475:IsA("Frame") then
			local v476 = 0;
			local v477 = functionBank.HasItem(v475.Name);
			if v477 then
				v476 = _G.data.inventory[v477].quantity;
			end;
			v475.Quantity.Text = v476;
			if v476 > 0 then
				v475.OpenButton.Text = "OPEN";
				v475.OpenButton.BackgroundColor3 = v19.goodGreen;
				v475.OpenButton.Visible = true;
				v475.Quantity.TextColor3 = v19.goodGreen;
			else
				v475.OpenButton.Text = ">> ";
				v475.OpenButton.BackgroundColor3 = v19.ironGrey;
				v475.Quantity.TextColor3 = Color3.fromRGB(255, 255, 255);
			end;
		end;	
	end;
	if _G.data.equipped then
		local v478 = v20[_G.data.toolbar[_G.data.equipped].name];
		if v478.toolType == "ranged" then
			l__MainGui__30.Panels.Stats.AmmoImage.Image = v20[v478.projectileName].image;
			local v479 = functionBank.HasItem(v478.projectileName);
			if v479 then
				l__MainGui__30.Panels.Stats.AmmoImage.ImageLabel.QuantityLabel.Text = _G.data.inventory[v479].quantity;
			else
				l__MainGui__30.Panels.Stats.AmmoImage.ImageLabel.QuantityLabel.Text = "0";
			end;
			l__MainGui__30.Panels.Stats.AmmoImage.Visible = true;
		end;
	else
		l__MainGui__30.Panels.Stats.AmmoImage.Visible = false;
	end;
	local l__next__480 = next;
	local v481, v482 = l__MainGui__30.RightPanel.Inventory.List:GetChildren();
	while true do
		local v483, v484 = l__next__480(v481, v482);
		if not v483 then
			break;
		end;
		v482 = v483;
		if v484:IsA("ImageLabel") then
			v484:Destroy();
		end;	
	end;
	local l__next__485 = next;
	local l__inventory__486 = _G.data.inventory;
	local v487 = nil;
	while true do
		local v488, v489 = l__next__485(l__inventory__486, v487);
		if not v488 then
			break;
		end;
		local v490 = true;
		if p104 and p104 ~= "all" then
			if v20[v489.name].itemType ~= p104 then
				print(v20[v489.name].itemType, "is  not", p104);
				v490 = false;
			else
				print("CATEGORY MATCH", v20[v489.name].itemType);
			end;
		end;
		if v20[v489.name].itemType ~= "dropChest" and v490 then
			local v491 = l__MainGui__30.RightPanel.Inventory.Templates.ItemFrame:Clone();
			v491.ImageButton.Image = v20[v489.name].image;
			v491.Name = v489.name;
			v491.ImageButton.InputBegan:connect(function(p105, p106)
				if p105.UserInputType == Enum.UserInputType.Touch and not u25 then
					print("dragging icon established", v491.Name);
					u25 = v491:Clone();
					u25.Size = UDim2.new(0, v491.AbsoluteSize.X, 0, v491.AbsoluteSize.Y);
					u25.AnchorPoint = Vector2.new(0.5, 0.5);
					u25.Parent = l__MainGui__30.TempEffects;
					while u25 do
						u25.Position = UDim2.new(0, l__mouse__26.X, 0, l__mouse__26.Y);
						l__RunService__1.RenderStepped:wait();					
					end;
				elseif p105.UserInputType == Enum.UserInputType.MouseButton1 then
					l__ReplicatedStorage__2.LocalSounds.Quicks.Click1:Play();
					print("USING ITEM,MOUSE INPUT");
					l__ReplicatedStorage__2.Events.UseBagltem:FireServer(v489.name);
					if v20[v489.name].nourishment then
						functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.Quicks.Eat, l__LocalPlayer__25.PlayerGui, true);
					end;
					if MainCounter >= 1 then
						SwingTool();
						MainCounter = 0;
						return;
					else
						MainCounter = MainCounter + 1;
						return;
					end;
				elseif p105.UserInputType == Enum.UserInputType.MouseButton2 then
					l__ReplicatedStorage__2.Events.DropBagItem:FireServer(v489.name);
				end;
			end);
			v491.Title.Text = v489.name;
			if l__UserInputService__3.MouseEnabled then
				v491.Title.Visible = false;
			else
				v491.Title.Visible = true;
			end;
			v491.ImageButton.MouseEnter:connect(function()
				v491.Title.Visible = true;
			end);
			v491.ImageButton.MouseLeave:connect(function()
				if l__UserInputService__3.MouseEnabled then
					v491.Title.Visible = false;
				end;
			end);
			if v489.quantity and v489.quantity > 0 then
				v491.QuantityImage.QuantityText.Text = v489.quantity;
			end;
			v491.Parent = l__MainGui__30.RightPanel.Inventory.List;
			v491.Visible = true;
		end;	
	end;
	local v492 = l__MainGui__30.RightPanel.Inventory.List.AbsoluteSize.X / 4 - 15;
	l__MainGui__30.RightPanel.Inventory.List.UIGridLayout.CellSize = UDim2.new(0, v492, 0, v492);
	l__MainGui__30.RightPanel.Inventory.List.CanvasSize = UDim2.new(0, 0, 0, l__MainGui__30.RightPanel.Inventory.List.UIGridLayout.AbsoluteContentSize.Y + 100);
	functionBank.UpdateBillboards();
end;
local u26 = {};
function v147.ToggleBusyTag(p107, p108)
	if p108 then
		u26[p107] = l__ReplicatedStorage__2.RelativeTime.Value;
		return;
	end;
	if u26[p107] then
		u26[p107] = nil;
	end;
end;
function v147.ClearBetweenPoints(p109, p110, p111)
	local v493, v494, v495, v496 = workspace:FindPartOnRayWithIgnoreList(Ray.new(p109, p110 - p109), p111);
	if v493 then
		return false;
	end;
	return true;
end;
function v147.GetDictionaryLength(p112)
	local v497 = 0;
	for v498, v499 in next, p112 do
		v497 = v497 + 1;
	end;
	return v497;
end;
local u27 = {};
function v147.SortToolbar()
	local l__next__500 = next;
	local v501, v502 = l__MainGui__30.Panels.Toolbar.List:GetChildren();
	while true do
		local v503, v504 = l__next__500(v501, v502);
		if not v503 then
			break;
		end;
		v502 = v503;
		if v504:IsA("ImageButton") then
			if functionBank.GetDictionaryLength(_G.data.toolbar[tonumber(v504.Name)]) > 0 and _G.data.toolbar[tonumber(v504.Name)].name ~= "none" then
				v504.Image = v20[_G.data.toolbar[tonumber(v504.Name)].name].image;
			else
				v504.Image = "";
			end;
			if tonumber(v504.Name) == _G.data.equipped then
				v504.ActiveIcon.Visible = true;
				v504.InactiveIcon.Visible = false;
			else
				v504.ActiveIcon.Visible = false;
				v504.InactiveIcon.Visible = true;
			end;
		end;	
	end;
	if _G.data.equipped == nil then
		l__MainGui__30.Panels.Toolbar.Title.Visible = false;
		for v505, v506 in next, u27 do
			v506:Stop();
		end;
		l__MainGui__30.Panels.Stats.AmmoImage.Visible = false;
		return;
	end;
	if _G.data.equipped ~= nil then
		if functionBank.GetDictionaryLength(_G.data.toolbar[_G.data.equipped]) > 0 then
			for v507, v508 in next, u27 do
				v508:Stop();
			end;
			if v20[_G.data.toolbar[_G.data.equipped].name].idleAnim then
				u27[v20[_G.data.toolbar[_G.data.equipped].name].idleAnim]:Play();
			end;
			local v509 = u13:WaitForChild(_G.data.toolbar[_G.data.equipped].name, 2);
			if v509 then
				local l__next__510 = next;
				local v511, v512 = v509:GetChildren();
				while true do
					local v513, v514 = l__next__510(v511, v512);
					if not v513 then
						break;
					end;
					v512 = v513;
					if v514.Name == "Draw" then
						v514.Transparency = 1;
					elseif v514.Name == "Rest" then
						v514.Transparency = 0;
					end;				
				end;
			end;
		end;
		local v515 = v20[_G.data.toolbar[_G.data.equipped].name];
		if v515.toolType == "ranged" then
			l__MainGui__30.Panels.Stats.AmmoImage.Image = v20[v515.projectileName].image;
			local v516 = functionBank.HasItem(v515.projectileName);
			if v516 then
				l__MainGui__30.Panels.Stats.AmmoImage.ImageLabel.QuantityLabel.Text = _G.data.inventory[v516].quantity;
			else
				l__MainGui__30.Panels.Stats.AmmoImage.ImageLabel.QuantityLabel.Text = "0";
			end;
			l__MainGui__30.Panels.Stats.AmmoImage.Visible = true;
		end;
	end;
end;
functionBank = v147;
functionBank.SortToolbar();
functionBank.DrawInventory();
functionBank.DrawCraftMenu();
functionBank.UpdateCosmetics();
functionBank.UpdateBoosts();
functionBank.UpdateGPList();
functionBank.DrawTribeGui();
functionBank.OpenGui();
functionBank.UpdateStats();
functionBank.UpdateMojoMenu();
l__MainGui__30.LeftPanel.CodesLeft.Frame.CreateButton.MouseButton1Down:Connect(function()
	functionBank.RedeemCode();
end);
l__SpawnGui__32.Customization.PlayButton.InputBegan:connect(function(p113, p114)
	if functionBank.InteractInput(p113, p114) then
		_G.data.hasSpawned = true;
		u12.CameraType = Enum.CameraType.Custom;
		u3 = false;
		ToggleOtherCharacters(true);
		l__ReplicatedStorage__2.Events.SpawnFirst:FireServer();
		l__StarterGui__4:SetCore("TopbarEnabled", true);
	end;
end);
local l__next__517 = next;
local v518, v519 = l__MainGui__30.Panels.Card.List:GetChildren();
while true do
	local v520, v521 = l__next__517(v518, v519);
	if not v520 then
		break;
	end;
	v519 = v520;
	if v521:IsA("Frame") then
		v521.ImageButton.InputBegan:connect(function(p115, p116)
			if functionBank.InteractInput(p115, p116) then
				functionBank.OpenGui(v521);
			end;
		end);
	end;
end;
ghost = nil;
local l__next__522 = next;
local v523, v524 = l__MainGui__30.Panels.Toolbar.List:GetChildren();
while true do
	local v525, v526 = l__next__522(v523, v524);
	if not v525 then
		break;
	end;
	v524 = v525;
	if v526:IsA("ImageButton") then
		v526.DragBegin:connect(function(p117)
			ghost = v526:Clone();
			ghost.Size = UDim2.new(0, v526.AbsoluteSize.X, 0, v526.AbsoluteSize.Y);
			ghost.AnchorPoint = Vector2.new(0.5, 0.5);
			ghost.Parent = l__MainGui__30.TempEffects;
			while ghost do
				l__RunService__1.RenderStepped:wait();
				ghost.Position = UDim2.new(0, l__mouse__26.X, 0, l__mouse__26.Y);			
			end;
		end);
		v526.DragStopped:connect(function(p118, p119)
			if ghost then
				ghost:Destroy();
			end;
			local v527 = nil;
			local l__next__528 = next;
			local v529, v530 = l__MainGui__30.Panels.Toolbar.List:GetChildren();
			while true do
				local v531, v532 = l__next__528(v529, v530);
				if not v531 then
					break;
				end;
				v530 = v531;
				if v532:IsA("ImageButton") and v532.AbsolutePosition.X <= p118 and p118 <= v532.AbsolutePosition.X + v532.AbsoluteSize.X and v532.AbsolutePosition.Y <= p119 and p119 <= v532.AbsolutePosition.Y + v532.AbsoluteSize.Y then
					v527 = v532;
					break;
				end;			
			end;
			if v527 == v526 then
				l__ReplicatedStorage__2.Events.EquipTool:FireServer(tonumber(v526.Name));
				l__MainGui__30.Panels.Toolbar.Title.Visible = true;
				l__MainGui__30.Panels.Toolbar.Title.Text = string.upper(_G.data.toolbar[tonumber(v526.Name)].name);
				l__ReplicatedStorage__2.LocalSounds.Quicks.ToolSwitch:Play();
				return;
			end;
			if v527 and v527 ~= v526 then
				l__ReplicatedStorage__2.Events.ToolSwap:FireServer(tonumber(v526.Name), tonumber(v527.Name));
				return;
			end;
			l__ReplicatedStorage__2.LocalSounds.Quicks.Click1:Play();
			if l__mouse__26.X < u12.ViewportSize.X * 0.75 and l__mouse__26.Y < u12.ViewportSize.Y * 0.9 then
				print("left 3/4 and top 9/10th, drop it");
				l__ReplicatedStorage__2.Events.DropBagItem:FireServer(tonumber(v526.Name));
				return;
			end;
			if not (u12.ViewportSize.X * 0.75 < l__mouse__26.X) or not (l__mouse__26.Y < u12.ViewportSize.Y * 0.9) then
				return;
			end;
			if not l__MainGui__30.RightPanel.Inventory.Visible then
				l__ReplicatedStorage__2.Events.DropBagItem:FireServer(tonumber(v526.Name));
				return;
			end;
			print("right 1/4 and top 9/10th, drop it");
			l__ReplicatedStorage__2.Events.Retool:FireServer(tonumber(v526.Name));
		end);
		v526.InputBegan:connect(function(p120, p121)
			if p121 then
				return;
			end;
			if p120.UserInputType == Enum.UserInputType.MouseButton2 and functionBank.GetDictionaryLength(_G.data.toolbar[tonumber(v526.Name)]) > 0 and _G.data.toolbar[tonumber(v526.Name)].name ~= "none" then
				l__ReplicatedStorage__2.Events.Retool:FireServer(tonumber(v526.Name));
			end;
		end);
	end;
end;
function lerp(p122, p123, p124)
	return p122 * (1 - p124) + p123 * p124;
end;
function ObjectWithinStuds(p125, p126)
	if (u7.Position - p125.Position).magnitude <= p126 then
		return true;
	end;
	return false;
end;
function ScanArray(p127, p128)
	local l__next__533 = next;
	local v534 = nil;
	while true do
		local v535, v536 = l__next__533(p127, v534);
		if v535 then

		else
			break;
		end;
		v534 = v535;
		if v536 == p128 then
			return false;
		end;	
	end;
	return true;
end;
function FadeTrack(p129, p130, p131)
	l__TweenService__6:Create(p129, TweenInfo.new(p130 and 5, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut, 0, false, p131), {
		Volume = 0
	}):Play();
end;
function PartsAlongRay(p132)
	local v537 = {};
	while true do
		local v538, v539 = workspace:FindPartOnRayWithIgnoreList(p132, v537);
		if v538 ~= workspace.Terrain then
			v537[#v537 + 1] = v538;
		end;
		if v538 then

		else
			break;
		end;
		if v538 ~= workspace.Terrain then

		else
			break;
		end;	
	end;
	return v537;
end;
coroutine.wrap(function()
	while wait(1) do
		local v540 = l__ReplicatedStorage__2.Events.Pinger:InvokeServer();
		ping = math.clamp(l__ReplicatedStorage__2.RelativeTime.Value - l__ReplicatedStorage__2.RelativeTime.Value, 0, 0.3);	
	end;
end)();
local u28 = nil;
local u29 = true;
local u30 = nil;
local u31 = false;
local u32 = false;
function SetupCharacter(p133)
	u13 = p133;
	u7 = p133:WaitForChild("HumanoidRootPart");
	u28 = p133:WaitForChild("Head");
	u22 = p133:WaitForChild("Humanoid");
	u12 = workspace.CurrentCamera;
	u12.FieldOfView = 65;
	game.Lighting.Bloom.Size = 13;
	if not _G.data.hasSpawned then
		u3 = true;
		ToggleOtherCharacters(false);
		u12.CameraType = Enum.CameraType.Scriptable;
		u29 = false;
		l__PlayerGui__29.SpawnGui.Enabled = true;
		l__PlayerGui__29.MainGui.Enabled = false;
		u12.CFrame = l__ReplicatedStorage__2.SpawnCamCF.Value;
		return;
	end;
	u12.CameraType = Enum.CameraType.Custom;
	u29 = true;
	l__PlayerGui__29.SpawnGui.Enabled = false;
	l__PlayerGui__29.MainGui.Enabled = true;
	l__ReplicatedStorage__2.LocalSounds.Music.BeautyMusic:Play();
	if not _G.data.hasSpawned then
		FadeTrack(l__ReplicatedStorage__2.LocalSounds.Music.BeautyMusic, 50, 30);
		spawn(function()
			wait(4);
			functionBank.MakeToast({
				title = "YOU:", 
				message = "...Where am I?", 
				color = v19.brownUI, 
				image = "", 
				duration = 6
			});
			wait(6);
			if not _G.data.hasSpawned then
				functionBank.MakeToast({
					title = "YOU:", 
					message = "I should make a raft...", 
					color = v19.brownUI, 
					image = "", 
					duration = 8
				});
				wait(4);
			end;
			if not _G.data.hasSpawned then
				functionBank.CreateNotification("Press C to open your bag!", v19.badRed, 4);
			end;
			wait(14);
			if not _G.data.hasSpawned then
				functionBank.CreateNotification(l__LocalPlayer__25.Name .. "! Press C to open your bag!", v19.badRed, 6);
			end;
		end);
	else
		FadeTrack(l__ReplicatedStorage__2.LocalSounds.Music.BeautyMusic, 30, 0);
	end;
	while true do
		if not u13.Parent then
			wait();
		end;
		if u13.Parent ~= workspace then

		else
			break;
		end;	
	end;
	u12.CameraType = Enum.CameraType.Custom;
	u22.HealthChanged:connect(function()
		functionBank.UpdateStats();
	end);
	u22.StateChanged:connect(function(p134, p135)
		if u22:GetState() == Enum.HumanoidStateType.Swimming then
			u22:ChangeState(Enum.HumanoidStateType.Running);
			l__LocalPlayer__25:Kick();
		end;
		if p135 == Enum.HumanoidStateType.Swimming then
			u22:ChangeState(p134);
			l__LocalPlayer__25:Kick();
		end;
		if u22:GetState() == Enum.HumanoidStateType.Seated then

		else
			u29 = true;
			return;
		end;
		u13.Head:FindFirstChild("Running"):Stop();
		u29 = false;
	end);
	u22.Died:connect(function()
		u29 = false;
	end);
	u22:SetStateEnabled(Enum.HumanoidStateType.Swimming, false);
	u22:SetStateEnabled(Enum.HumanoidStateType.RunningNoPhysics, false);
	u22:SetStateEnabled(Enum.HumanoidStateType.PlatformStanding, false);
	u30 = u7;
	u31 = true;
	u32 = true;
	u27 = {};
	coroutine.wrap(function()
		local l__next__541 = next;
		local v542, v543 = l__ReplicatedStorage__2.Animations:GetChildren();
		while true do
			local v544, v545 = l__next__541(v542, v543);
			if v544 then

			else
				break;
			end;
			v543 = v544;
			u27[v545.Name] = u22:LoadAnimation((v545:Clone()));
			wait();		
		end;
	end)();
end;
if l__LocalPlayer__25.Character then
	SetupCharacter(l__LocalPlayer__25.Character);
end;
l__LocalPlayer__25.CharacterAdded:connect(function(p136)
	SetupCharacter(p136);
	p136.DescendantAdded:connect(function(p137)
		if p137:IsA("Tool") or p137:IsA("HopperBin") then
			print("lmao f3x tools detected");
			l__LocalPlayer__25:Kick();
		end;
	end);
end);
local v546 = Instance.new("SelectionBox");
v546.Parent = workspace;
v546.Color3 = Color3.fromRGB(170, 255, 0);
local u33 = tick();
local u34 = false;
l__RunService__1.RenderStepped:connect(function()
	l__MainGui__30.Panels.MouseFrame.Position = UDim2.new(0, l__mouse__26.X + 40, 0, l__mouse__26.Y + 10);
	u22.AutoRotate = not _G.data.userSettings.camLock;
	workspace.Gravity = 196.2;
	if u32 and u7 then
		if u11 then
			u11.CFrame = u7.CFrame * CFrame.new(0, 100, 0);
		end;
		local v547 = Vector3.new(u7.Velocity.X, 0, u7.Velocity.Z);
		if v547.magnitude > 30 then
			print(v547);
			print("throtttle");
			u7.Velocity = Vector3.new(0, 0, 0);
		end;
		local v548, v549, v550, v551 = workspace:FindPartOnRay(Ray.new(u7.Position + Vector3.new(0, 5, 0), Vector3.new(0, -15, 0)), u13);
		if v551 == Enum.Material.Water and (not functionBank.HasMojoRecipe("Water Walker") or _G.data.disabledMojo["Water Walker"]) then
			u22.WalkSpeed = 6.4;
		else
			u22.WalkSpeed = 16;
		end;
		local v552 = u12.CFrame * CFrame.new(0, 0, -1000);
		if u32 and u7 and not l__UserInputService__3:IsKeyDown(Enum.KeyCode.LeftControl) then
			local v553 = true;
			local v554, v555, v556, v557 = workspace:FindPartOnRay(Ray.new(u7.Position, Vector3.new(0, -10, 0)), u13);
			if v554 and (v554.Name == "VehicleSeat" or v554.Name == "Seat") then
				v553 = false;
				if v554.Name == "VehicleSeat" and u22:GetState() == Enum.HumanoidStateType.Seated then
					local v558, v559 = functionBank.MiddleScreenRay();
					v554.LookEvent:FireServer(v559);
				end;
			end;
			if u29 and v553 and _G.data.userSettings.camLock then
				local v560 = CFrame.new(u7.Position, Vector3.new(v552.p.x, u7.Position.Y, v552.p.z));
				u7.CFrame = u7.CFrame:lerp(v560, 0.2125);
				if u7.CFrame.lookVector:Dot(v560.lookVector) < 5 and tick() - u33 > 1 then
					u7.CFrame = v560;
				end;
				u33 = tick();
			end;
		end;
	end;
	if not _G.data.hasSpawned then
		u22.WalkSpeed = 0;
		u22.JumpPower = 0;
	end;
	if u32 and u7 and u28 then
		if (u12.CFrame.p - u28.Position).magnitude < 1.5 and _G.data.equipped then
			local l__next__561 = next;
			local v562, v563 = u13:GetDescendants();
			while true do
				local v564, v565 = l__next__561(v562, v563);
				if not v564 then
					break;
				end;
				v563 = v564;
				if v565:IsA("BasePart") then
					if v565.Name ~= "GhostRightArm" and v565.Parent.Name ~= _G.data.toolbar[_G.data.equipped].name then
						v565.LocalTransparencyModifier = 1;
					else
						v565.LocalTransparencyModifier = 0;
					end;
				end;			
			end;
		elseif u13:FindFirstChild("GhostRightArm") then
			u13.GhostRightArm.LocalTransparencyModifier = 1;
		end;
	end;
	if not u32 or not u7 then
		l__mouse__26.Icon = "";
		v546.Adornee = nil;
		return;
	end;
	if not l__mouse__26.Target then
		l__mouse__26.Icon = "";
		v546.Adornee = nil;
		return;
	end;
	if not l__mouse__26.Target:FindFirstChild("Draggable") and (not l__mouse__26.Target.Parent:FindFirstChild("Draggable") and not u23) then
		if (l__mouse__26.Target:FindFirstChild("DoorButton") or l__mouse__26:FindFirstChild("OpenGuiPanel")) and ObjectWithinStuds(l__mouse__26.Target, 25) then
			l__mouse__26.Icon = "http://www.roblox.com/asset/?id=455570287";
		elseif l__mouse__26.Target.Parent:FindFirstChild("Interactable") then
			if l__mouse__26.Target.Parent:FindFirstChild("InteractPart") then
				v546.Adornee = l__mouse__26.Target.Parent.InteractPart;
			else
				v546.Adornee = l__mouse__26.Target.Parent;
			end;
		elseif not l__mouse__26.Target:FindFirstChild("Health") and not l__mouse__26.Target.Parent:FindFirstChild("Health") then
			if not (not l__mouse__26.Target.Parent:FindFirstChild("Humanoid")) and not (not _G.data.equipped) and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 or u34 then
				l__mouse__26.Icon = "rbxassetid://117431027";
			else
				l__mouse__26.Icon = "";
				v546.Adornee = nil;
			end;
		elseif not (not _G.data.equipped) and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 or u34 then
			l__mouse__26.Icon = "rbxassetid://117431027";
		else
			l__mouse__26.Icon = "";
			v546.Adornee = nil;
		end;
	elseif ObjectWithinStuds(l__mouse__26.Target, 25) then
		l__mouse__26.Icon = "http://www.roblox.com/asset/?id=455570287";
	elseif l__mouse__26.Target.Parent:FindFirstChild("Interactable") then
		if l__mouse__26.Target.Parent:FindFirstChild("InteractPart") then
			v546.Adornee = l__mouse__26.Target.Parent.InteractPart;
		else
			v546.Adornee = l__mouse__26.Target.Parent;
		end;
	elseif not l__mouse__26.Target:FindFirstChild("Health") and not l__mouse__26.Target.Parent:FindFirstChild("Health") then
		if not (not l__mouse__26.Target.Parent:FindFirstChild("Humanoid")) and not (not _G.data.equipped) and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 or u34 then
			l__mouse__26.Icon = "rbxassetid://117431027";
		else
			l__mouse__26.Icon = "";
			v546.Adornee = nil;
		end;
	elseif not (not _G.data.equipped) and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 or u34 then
		l__mouse__26.Icon = "rbxassetid://117431027";
	else
		l__mouse__26.Icon = "";
		v546.Adornee = nil;
	end;
	local v566 = nil;
	if l__mouse__26.Target:FindFirstChild("Pickup") then
		v566 = l__mouse__26.Target.Name;
	elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
		v566 = l__mouse__26.Target.Parent.Name;
	end;
	if not v566 or not ObjectWithinStuds(l__mouse__26.Target, 25) then
		l__MainGui__30.Panels.MouseFrame.Visible = false;
		return;
	end;
	if v566 == "Coin2" then
		l__MainGui__30.Panels.MouseFrame.Title.Text = "Coin";
	else
		l__MainGui__30.Panels.MouseFrame.Title.Text = v566;
	end;
	l__MainGui__30.Panels.MouseFrame.ELabel.Text = "F - harvest";
	l__MainGui__30.Panels.MouseFrame.Visible = true;
	if v20[v566] and v20[v566].nourishment then
		l__MainGui__30.Panels.MouseFrame.FLabel.Text = "E - eat";
		return;
	end;
	if l__mouse__26.Target.Material == Enum.Material.Water then
		l__MainGui__30.Panels.MouseFrame.FLabel.Text = "E - drink";
		return;
	end;
	l__MainGui__30.Panels.MouseFrame.FLabel.Text = "";
end);
local u35 = nil;
function DragFunction()
	if not u35 then
		u35 = Instance.new("BodyPosition");
		u35.Parent = u23;
		u35.P = 25000;
		u35.D = 1500;
		u35.MaxForce = Vector3.new(math.huge, math.huge, math.huge);
		u35.AncestryChanged:connect(function()
			if u35 then
				if not u35.Parent then
					u35 = nil;
				end;
			else
				u35 = nil;
			end;
		end);
	end;
	if u23 then
		if u35 then
			if u23.Parent then
				if u23.Parent:IsA("Model") then
					if u23.Parent ~= workspace then
						l__mouse__26.TargetFilter = u23.Parent;
					else
						l__mouse__26.TargetFilter = u23;
					end;
				else
					l__mouse__26.TargetFilter = u23;
				end;
			else
				l__mouse__26.TargetFilter = u23;
			end;
			if not u23:FindFirstChild("Draggable") then
				if u23.Parent then
					if u23.Parent:FindFirstChild("Draggable") then
						local v567 = Ray.new(u7.Position, (l__mouse__26.Hit.p - u7.Position).unit * math.clamp((u7.Position - l__mouse__26.Hit.p).magnitude, 3, 30));
						local v568, v569 = workspace:FindPartOnRayWithIgnoreList(v567, PartsAlongRay(v567));
						u35.Position = v569 + Vector3.new(0, u23.Size.Y / 2, 0);
					end;
				end;
			else
				v567 = Ray.new(u7.Position, (l__mouse__26.Hit.p - u7.Position).unit * math.clamp((u7.Position - l__mouse__26.Hit.p).magnitude, 3, 30));
				v568, v569 = workspace:FindPartOnRayWithIgnoreList(v567, PartsAlongRay(v567));
				u35.Position = v569 + Vector3.new(0, u23.Size.Y / 2, 0);
			end;
		end;
	end;
end;
local u36 = false;
local u37 = nil;
local u38 = 0;
function SwingTool()
	if _G.data.equipped then
		if u36 then
			u36 = false;
			return;
		end;
		u37 = l__LocalPlayer__25.Character:FindFirstChild(_G.data.toolbar[_G.data.equipped].name);
		if v20[_G.data.toolbar[_G.data.equipped].name].speed <= l__ReplicatedStorage__2.RelativeTime.Value - _G.data.toolbar[_G.data.equipped].lastSwing then
			_G.data.toolbar[_G.data.equipped].lastSwing = l__ReplicatedStorage__2.RelativeTime.Value;
			local l__name__570 = _G.data.toolbar[_G.data.equipped].name;
			local v571 = v20[_G.data.toolbar[_G.data.equipped].name];
			if v571.toolType == "ranged" then

			else
				v28.Size = Vector3.new(6, 11, 5);
				v28.CFrame = u13.PrimaryPart.CFrame * CFrame.new(0, -2, -v28.Size.Z / 2);
				v28.Parent = u13;
				v28.Parent = nil;
				local v572 = {};
				local l__next__573 = next;
				local v574 = v28:GetTouchingParts();
				local v575 = nil;
				while true do
					local v576, v577 = l__next__573(v574, v575);
					if v576 then

					else
						break;
					end;
					v575 = v576;
					if not v577:IsDescendantOf(u13) then
						if v577 == workspace.Terrain then

						else
							v572[#v572 + 1] = v577;
						end;
					end;				
				end;
				if v20[_G.data.toolbar[_G.data.equipped].name].useType == "Slash" then
					l__ReplicatedStorage__2.Events.SwingTool:FireServer(l__ReplicatedStorage__2.RelativeTime.Value, v572);
					if u37 then
						u27[v20[_G.data.toolbar[_G.data.equipped].name].useType]:Play();
						return;
					else
						return;
					end;
				elseif v20[_G.data.toolbar[_G.data.equipped].name].useType == "Horn" then
					u27[v20[_G.data.toolbar[_G.data.equipped].name].useType]:Play();
					l__ReplicatedStorage__2.Events.MusicTool:FireServer(l__ReplicatedStorage__2.RelativeTime.Value);
					return;
				elseif v20[_G.data.toolbar[_G.data.equipped].name].useType == "Target" then
					local v578 = u12:ScreenPointToRay(l__mouse__26.X, l__mouse__26.Y);
					l__ReplicatedStorage__2.Events.TargetTool:FireServer(l__ReplicatedStorage__2.RelativeTime.Value, functionBank.FirstPartOnRay(Ray.new(v578.Origin, v578.Direction * 2000), u13));
					return;
				else
					if v20[_G.data.toolbar[_G.data.equipped].name].useType == "Rod" then
						print("yoot");
						local v579 = u12:ScreenPointToRay(l__mouse__26.X, l__mouse__26.Y);
						l__ReplicatedStorage__2.Events.RodSwing:FireServer(l__ReplicatedStorage__2.RelativeTime.Value, (Ray.new(v579.Origin, v579.Direction * 2000)));
					end;
					return;
				end;
			end;
			if not functionBank.HasItem(v571.projectileName) then
				functionBank.CreateNotification("No ammo!", v19.badRed, 2);
				return;
			end;
			u34 = true;
			local l__next__580 = next;
			local v581, v582 = u13:WaitForChild(l__name__570):GetChildren();
			while true do
				local v583, v584 = l__next__580(v581, v582);
				if v583 then

				else
					break;
				end;
				v582 = v583;
				if v584.Name == "Draw" then
					v584.Transparency = 0;
				elseif v584.Name == "Rest" then
					v584.Transparency = 1;
				end;			
			end;
			if v571.pullSound then
				functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.BowSounds[v571.soundClass].Pullback, u7);
			end;
			u38 = 0;
			if l__UserInputService__3.MouseEnabled then
				if v20[l__name__570].drawAnim then
					u27[v20[l__name__570].drawAnim]:Play(v20[l__name__570].drawAnim.drawAnimLength);
				end;
				while true do
					if u34 then

					else
						break;
					end;
					u38 = math.clamp(u38 + 0.025, 0, v20[l__name__570].drawLength);
					u12.FieldOfView = 65 - u38 * 2;
					u22.WalkSpeed = 16 - u38 * 10;
					l__MainGui__30.Panels.Stats.Power.Visible = true;
					l__MainGui__30.Panels.Stats.Power.Slider.Size = UDim2.new(u38 / v20[l__name__570].drawLength, 0, 1, 0);
					l__RunService__1.RenderStepped:wait();				
				end;
			elseif l__UserInputService__3.TouchEnabled then
				if v20[l__name__570].drawAnim then
					u27[v20[l__name__570].drawAnim]:Play(v20[l__name__570].drawAnim, 0);
					u27[v20[l__name__570].drawAnim]:Stop(v20[l__name__570].drawAnim, 3);
				end;
				u34 = false;
				u38 = v20[l__name__570].drawLength;
			end;
			l__MainGui__30.Panels.Stats.Power.Visible = false;
			_G.data.toolbar[_G.data.equipped].lastSwing = l__ReplicatedStorage__2.RelativeTime.Value;
			functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.BowSounds[v571.soundClass].Fire, u7);
			local v585, v586 = functionBank.CursorRay();
			MakeProjectile(l__name__570, CFrame.new((u13.PrimaryPart.CFrame * CFrame.new(1.4, -0.4, -3)).p, v586), u38 / v20[l__name__570].drawLength, true);
			u38 = 0;
			u12.FieldOfView = 65;
			local l__next__587 = next;
			local v588, v589 = u13:WaitForChild(l__name__570):GetChildren();
			while true do
				local v590, v591 = l__next__587(v588, v589);
				if v590 then

				else
					break;
				end;
				v589 = v590;
				if v591.Name == "Draw" then
					v591.Transparency = 1;
				elseif v591.Name == "Rest" then
					v591.Transparency = 0;
				end;			
			end;
			if v20[l__name__570].drawAnim then
				u27[v20[l__name__570].drawAnim]:Stop(v20[l__name__570].drawAnimSlow);
			end;
			if v571.postFireSound then
				functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.BowSounds[v571.soundClass].PostFire, u7);
				return;
			end;
		end;
	end;
end;
l__UserInputService__3.TouchEnded:connect(function(p138, p139)
	if not p139 then
		SwingTool();
	end;
	if u25 then
		if l__mouse__26.X < u12.ViewportSize.X * 0.75 then
			l__ReplicatedStorage__2.Events.DropBagItem:FireServer(u25.Name);
			u25:Destroy();
			u25 = nil;
		else
			local v592 = nil;
			for v593, v594 in next, l__MainGui__30.RightPanel.Inventory.List:GetChildren() do
				if v594:IsA("ImageLabel") and v594.AbsolutePosition.X <= l__mouse__26.X and l__mouse__26.X <= v594.AbsolutePosition.X + v594.AbsoluteSize.X and v594.AbsolutePosition.Y <= l__mouse__26.Y and l__mouse__26.Y <= v594.AbsolutePosition.Y + v594.AbsoluteSize.Y then
					v592 = v594;
					break;
				end;
			end;
			if v592 and v592.Name == u25.Name then
				if v20[u25.name].nourishment then
					functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.Quicks.Eat, l__LocalPlayer__25.PlayerGui, true);
				end;
				l__ReplicatedStorage__2.Events.UseBagltem:FireServer(u25.Name);
			end;
			u25:Destroy();
			u25 = nil;
		end;
	end;
	u5 = nil;
	u6 = 0;
end);
function PlaceStructureFunction()
	if u14 then
		if l__UserInputService__3.MouseEnabled then

		else
			if l__UserInputService__3.TouchEnabled then
				l__ReplicatedStorage__2.Events.PlaceStructure:FireServer(u14.Name, u14.PrimaryPart.CFrame, u15);
				functionBank.ClearMouseBoundStructure();
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Bag);
			end;
			return;
		end;
	else
		return;
	end;
	l__ReplicatedStorage__2.Events.PlaceStructure:FireServer(u14.Name, u14.PrimaryPart.CFrame, u15);
	functionBank.ClearMouseBoundStructure();
	functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Bag);
end;
l__UserInputService__3.TouchMoved:connect(function(p140, p141)
	if not p141 then
		u36 = true;
	end;
end);
local u39 = {
	pickup = Enum.KeyCode.F, 
	eat = Enum.KeyCode.E, 
	rotate = Enum.KeyCode.R, 
	toggleBag = Enum.KeyCode.C, 
	toggleTribe = Enum.KeyCode.T, 
	toggleSettings = Enum.KeyCode.X, 
	toggleShop = Enum.KeyCode.Z, 
	toggleMojo = Enum.KeyCode.K
};
local u40 = false;
local u41 = false;
l__UserInputService__3.InputBegan:connect(function(p142, p143)
	if p143 then
		return;
	end;
	local l__KeyCode__595 = p142.KeyCode;
	if p142.UserInputType == Enum.UserInputType.MouseWheel then
		return;
	end;
	if p142.UserInputType == Enum.UserInputType.Gamepad1 then
		if p142.KeyCode == Enum.KeyCode.ButtonA then
			return;
		end;
	elseif p142.UserInputType == Enum.UserInputType.Keyboard then
		local v596 = p142.KeyCode.Value - 48;
		if v596 >= 1 and v596 <= 6 then
			if v596 == _G.data.equipped or functionBank.GetDictionaryLength(_G.data.toolbar[v596]) == 0 then
				for v597, v598 in next, u27 do
					v598:Stop();
				end;
				_G.data.equipped = nil;
			elseif v596 ~= _G.data.equipped and functionBank.GetDictionaryLength(_G.data.toolbar[v596]) > 0 then
				_G.data.equipped = v596;
				l__MainGui__30.Panels.Toolbar.Title.Visible = true;
				l__MainGui__30.Panels.Toolbar.Title.Text = string.upper(_G.data.toolbar[_G.data.equipped].name);
				l__ReplicatedStorage__2.LocalSounds.Quicks.ToolSwitch:Play();
			end;
			l__ReplicatedStorage__2.Events.EquipTool:FireServer(v596);
			functionBank.SortToolbar();
			return;
		end;
		if l__KeyCode__595 == Enum.KeyCode.V and _G.data.spell then
			local v599, v600, v601, v602 = functionBank.CursorRay();
			l__ReplicatedStorage__2.Events.VoodooSpell:FireServer(v600);
			return;
		end;
		if l__KeyCode__595 == Enum.KeyCode.R then
			if u23 then
				u23.CFrame = CFrame.new(u23.CFrame.p) * CFrame.Angles(0, u15, 0);
				u23.Velocity = Vector3.new(0, 0, 0);
				return;
			end;
			if u14 then
				while l__UserInputService__3:IsKeyDown(Enum.KeyCode.R) do
					u15 = u15 + 3;
					l__RunService__1.RenderStepped:wait();				
				end;
			end;
		elseif l__KeyCode__595 == Enum.KeyCode.Q then
			if u23 then
				u23.CFrame = CFrame.new(u23.CFrame.p) * CFrame.Angles(0, u15, 0);
				u23.Velocity = Vector3.new(0, 0, 0);
				return;
			end;
			if u14 then
				while l__UserInputService__3:IsKeyDown(Enum.KeyCode.Q) do
					u15 = u15 - 3;
					l__RunService__1.RenderStepped:wait();				
				end;
			end;
		elseif l__KeyCode__595 == u39.pickup then
			if l__mouse__26.Target then
				if not l__mouse__26.Target:FindFirstChild("Pickup") then
					if l__mouse__26.Target.Parent:FindFirstChild("Pickup") and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
						if l__UserInputService__3.TouchEnabled then
							u36 = true;
						end;
						u8 = true;
						u9 = os.clock();
						local v603 = nil;
						if l__mouse__26.Target:FindFirstChild("Pickup") then
							v603 = l__mouse__26.Target;
						elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
							v603 = l__mouse__26.Target.Parent;
						end;
						if functionBank.CanBearLoad(v603.Name) then
							l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
							l__ReplicatedStorage__2.Events.Pickup:FireServer(v603);
							if ping <= 0.001 then
								return;
							else
								functionBank.CollectPart(v603);
								return;
							end;
						else
							functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
							return;
						end;
					end;
				elseif (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 then
					if l__UserInputService__3.TouchEnabled then
						u36 = true;
					end;
					u8 = true;
					u9 = os.clock();
					v603 = nil;
					if l__mouse__26.Target:FindFirstChild("Pickup") then
						v603 = l__mouse__26.Target;
					elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
						v603 = l__mouse__26.Target.Parent;
					end;
					if functionBank.CanBearLoad(v603.Name) then
						l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
						l__ReplicatedStorage__2.Events.Pickup:FireServer(v603);
						if ping <= 0.001 then
							return;
						else
							functionBank.CollectPart(v603);
							return;
						end;
					else
						functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
						return;
					end;
				end;
			end;
		elseif l__KeyCode__595 == u39.eat then
			local l__Target__604 = l__mouse__26.Target;
			if l__Target__604 and ((not (not v20[l__Target__604.Name]) and not (not v20[l__Target__604.Name].nourishment) and not (not l__Target__604:FindFirstChild("Pickup")) or l__Target__604.Material == Enum.Material.Water) and (l__Target__604.Position - u7.Position).magnitude <= 25 and l__Target__604 ~= workspace.Terrain) then
				l__ReplicatedStorage__2.Events.Consume:FireServer(l__Target__604);
				if not (ping <= 0.001) then
					if l__Target__604:IsA("BasePart") then
						functionBank.CreateParticles(l__ReplicatedStorage__2.Particles.Fissure, l__Target__604.CFrame.p, l__Target__604.CFrame.p + Vector3.new(0, 1, 0), math.random(2, 4), 4, {
							Color = ColorSequence.new(l__Target__604.Color, l__Target__604.Color)
						});
					end;
					l__Target__604:Destroy();
				end;
				functionBank.CreateSound(l__ReplicatedStorage__2.LocalSounds.Quicks.Eat, l__PlayerGui__29, true);
				return;
			end;
		else
			if l__KeyCode__595 == u39.toggleBag then
				print("TOGGLE  KEY REE");
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Bag);
				functionBank.ClearMouseBoundStructure();
				return;
			end;
			if l__KeyCode__595 == u39.toggleTribe then
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Tribe);
				functionBank.DrawTribeGui();
				functionBank.ClearMouseBoundStructure();
				return;
			end;
			if l__KeyCode__595 == u39.toggleSettings then
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Settings);
				return;
			end;
			if l__KeyCode__595 == u39.toggleShop then
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Shop);
				return;
			end;
			if l__KeyCode__595 == u39.toggleMojo then
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Mojo);
				return;
			end;
		end;
	elseif p142.UserInputType == Enum.UserInputType.MouseButton1 or p142.UserInputType == Enum.UserInputType.Touch then
		local v605 = nil;
		local v606 = nil;
		local v607 = nil;
		local v608, v609 = functionBank.CursorRay(workspace.Terrain);
		if v608 and v608.Name == "RadioButton" then
			v608.Clicker:FireServer();
			return;
		end;
		local v610 = nil;
		if p142.UserInputType == Enum.UserInputType.MouseButton1 then
			v610 = "mouse";
		elseif p142.UserInputType == Enum.UserInputType.Touch then
			v610 = "touch";
		end;
		if u14 then
			if v610 == "mouse" then
				PlaceStructureFunction();
				if l__UserInputService__3:IsKeyDown(Enum.KeyCode.LeftShift) then
					u40 = true;
					return;
				else
					functionBank.ClearMouseBoundStructure();
					functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Bag);
					functionBank.ClearMouseBoundStructure();
					return;
				end;
			else
				return;
			end;
		end;
		if l__mouse__26.Target then
			if not l__mouse__26.Target:FindFirstChild("Pickup") then
				if l__mouse__26.Target.Parent:FindFirstChild("Pickup") and (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 and v610 == "touch" then
					local v611 = nil;
					if l__mouse__26.Target:FindFirstChild("Pickup") then
						v611 = l__mouse__26.Target;
					elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
						v611 = l__mouse__26.Target.Parent;
					end;
					u5 = true;
					u6 = os.clock();
					if functionBank.CanBearLoad(v611.Name) then
						l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
						l__ReplicatedStorage__2.Events.Pickup:FireServer(v611);
						if not (ping <= 0.001) then
							functionBank.CollectPart(v611);
						end;
					else
						functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
					end;
				end;
			elseif (l__mouse__26.Target.Position - u7.Position).magnitude <= 25 and l__LocalPlayer__25.Character and l__LocalPlayer__25.Character.Humanoid and l__LocalPlayer__25.Character.Humanoid.Health > 0 and v610 == "touch" then
				v611 = nil;
				if l__mouse__26.Target:FindFirstChild("Pickup") then
					v611 = l__mouse__26.Target;
				elseif l__mouse__26.Target.Parent:FindFirstChild("Pickup") then
					v611 = l__mouse__26.Target.Parent;
				end;
				u5 = true;
				u6 = os.clock();
				if functionBank.CanBearLoad(v611.Name) then
					l__ReplicatedStorage__2.LocalSounds.Quicks.Pickup:Play();
					l__ReplicatedStorage__2.Events.Pickup:FireServer(v611);
					if not (ping <= 0.001) then
						functionBank.CollectPart(v611);
					end;
				else
					functionBank.CreateNotification("BAG FULL", v19.badRed, 1.3);
				end;
			end;
			if l__mouse__26.Target.Parent:FindFirstChild("Interactable") and ObjectWithinStuds(l__mouse__26.Target, 25) then
				local v612 = nil;
				local v613 = nil;
				local v614 = nil;
				local v615 = nil;
				local v616 = nil;
				local v617 = nil;
				local v618 = nil;
				local v619 = nil;
				local v620 = nil;
				local v621 = nil;
				local v622 = nil;
				local v623 = nil;
				local v624 = nil;
				local v625 = nil;
				local v626 = nil;
				local v627 = nil;
				local v628 = nil;
				local v629 = nil;
				local v630 = nil;
				local v631 = nil;
				local v632 = nil;
				local v633 = nil;
				local v634 = nil;
				local v635 = nil;
				local v636 = nil;
				local v637 = nil;
				local v638 = nil;
				local v639 = nil;
				local v640 = nil;
				local v641 = nil;
				local v642 = nil;
				local v643 = nil;
				local v644 = nil;
				local v645 = nil;
				local v646 = nil;
				local v647 = nil;
				local v648 = nil;
				local v649 = nil;
				local v650 = nil;
				local v651 = nil;
				local v652 = nil;
				local v653 = nil;
				local v654 = nil;
				local v655 = nil;
				print("DO IT YO");
				if u21 then
					if u21 == l__mouse__26.Target.Parent then
						if l__PlayerGui__29:FindFirstChild(u21.Name) then
							l__PlayerGui__29:FindFirstChild(u21.Name):Destroy();
							u21 = nil;
						end;
						return;
					else
						if l__PlayerGui__29:FindFirstChild(u21.Name) then
							l__PlayerGui__29:FindFirstChild(u21.Name):Destroy();
							u21 = nil;
						end;
						v612 = l__mouse__26;
						v613 = "Target";
						v614 = v612;
						v615 = v613;
						v616 = v614[v615];
						local v656 = "Parent";
						v617 = v616;
						v618 = v656;
						v619 = v617[v618];
						v620 = v619;
						u21 = v620;
						local v657 = functionBank;
						local v658 = "CreateSound";
						v621 = v657;
						v622 = v658;
						local v659 = v621[v622];
						v623 = l__ReplicatedStorage__2;
						local v660 = "LocalSounds";
						v624 = v623;
						v625 = v660;
						v626 = v624[v625];
						local v661 = "Quicks";
						v627 = v626;
						v628 = v661;
						local v662 = v627[v628];
						local v663 = "UIToggle";
						v629 = v662;
						v630 = v663;
						local v664 = v629[v630];
						local v665 = l__LocalPlayer__25;
						local v666 = "PlayerGui";
						v631 = v665;
						v632 = v666;
						local v667 = v631[v632];
						v633 = v659;
						v634 = v664;
						v635 = v667;
						v633(v634, v635);
						local v668 = l__ReplicatedStorage__2;
						local v669 = "Guis";
						v636 = v668;
						v637 = v669;
						local v670 = v636[v637];
						v638 = l__mouse__26;
						local v671 = "Target";
						v639 = v638;
						v640 = v671;
						local v672 = v639[v640];
						local v673 = "Parent";
						v641 = v672;
						v642 = v673;
						local v674 = v641[v642];
						local v675 = "Name";
						v643 = v674;
						v644 = v675;
						local v676 = v643[v644];
						local v677 = "FindFirstChild";
						v645 = v670;
						local v678 = v645;
						v646 = v670;
						v647 = v677;
						local v679 = v646[v647];
						v648 = v679;
						v649 = v678;
						v650 = v676;
						local v680 = v648(v649, v650);
						v651 = v680;
						if v651 then
							v680 = v680:Clone();
						end;
						v652 = v680;
						if v652 then
							v680.Parent = l__PlayerGui__29;
							v680.Adornee = l__mouse__26.Target.Parent.PrimaryPart;
							v680.Frame.List.Exit.MouseButton1Down:connect(function()
								u21 = nil;
								v680:Destroy();
							end);
						end;
						local v681 = functionBank;
						local v682 = "UpdateBillboards";
						v653 = v681;
						v654 = v682;
						local v683 = v653[v654];
						v655 = v683;
						v655();
						return;
					end;
				else
					v612 = l__mouse__26;
					v613 = "Target";
					v614 = v612;
					v615 = v613;
					v616 = v614[v615];
					v656 = "Parent";
					v617 = v616;
					v618 = v656;
					v619 = v617[v618];
					v620 = v619;
					u21 = v620;
					v657 = functionBank;
					v658 = "CreateSound";
					v621 = v657;
					v622 = v658;
					v659 = v621[v622];
					v623 = l__ReplicatedStorage__2;
					v660 = "LocalSounds";
					v624 = v623;
					v625 = v660;
					v626 = v624[v625];
					v661 = "Quicks";
					v627 = v626;
					v628 = v661;
					v662 = v627[v628];
					v663 = "UIToggle";
					v629 = v662;
					v630 = v663;
					v664 = v629[v630];
					v665 = l__LocalPlayer__25;
					v666 = "PlayerGui";
					v631 = v665;
					v632 = v666;
					v667 = v631[v632];
					v633 = v659;
					v634 = v664;
					v635 = v667;
					v633(v634, v635);
					v668 = l__ReplicatedStorage__2;
					v669 = "Guis";
					v636 = v668;
					v637 = v669;
					v670 = v636[v637];
					v638 = l__mouse__26;
					v671 = "Target";
					v639 = v638;
					v640 = v671;
					v672 = v639[v640];
					v673 = "Parent";
					v641 = v672;
					v642 = v673;
					v674 = v641[v642];
					v675 = "Name";
					v643 = v674;
					v644 = v675;
					v676 = v643[v644];
					v677 = "FindFirstChild";
					v645 = v670;
					v678 = v645;
					v646 = v670;
					v647 = v677;
					v679 = v646[v647];
					v648 = v679;
					v649 = v678;
					v650 = v676;
					v680 = v648(v649, v650);
					v651 = v680;
					if v651 then
						v680 = v680:Clone();
					end;
					v652 = v680;
					if v652 then
						v680.Parent = l__PlayerGui__29;
						v680.Adornee = l__mouse__26.Target.Parent.PrimaryPart;
						v680.Frame.List.Exit.MouseButton1Down:connect(function()
							u21 = nil;
							v680:Destroy();
						end);
					end;
					v681 = functionBank;
					v682 = "UpdateBillboards";
					v653 = v681;
					v654 = v682;
					v683 = v653[v654];
					v655 = v683;
					v655();
					return;
				end;
			end;
			if not l__mouse__26.Target:FindFirstChild("Draggable") then
				if l__mouse__26.Target.Parent:FindFirstChild("Draggable") and ObjectWithinStuds(l__mouse__26.Target, 25) and v610 == "mouse" and v610 == "mouse" then
					print("draggable and found mouse");
					u23 = l__mouse__26.Target;
					if l__mouse__26.Target:FindFirstChild("Draggable") then
						functionBank.RestorePhysicality(u23);
						l__ReplicatedStorage__2.Events.ForceInteract:FireServer(u23);
					elseif l__mouse__26.Target.Parent:FindFirstChild("Draggable") then
						functionBank.RestorePhysicality(u23);
						l__ReplicatedStorage__2.Events.ForceInteract:FireServer(u23.Parent);
					end;
					l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
					l__RunService__1:BindToRenderStep("Dragger", Enum.RenderPriority.Camera.Value - 1, DragFunction);
					return;
				end;
			elseif ObjectWithinStuds(l__mouse__26.Target, 25) and v610 == "mouse" and v610 == "mouse" then
				print("draggable and found mouse");
				u23 = l__mouse__26.Target;
				if l__mouse__26.Target:FindFirstChild("Draggable") then
					functionBank.RestorePhysicality(u23);
					l__ReplicatedStorage__2.Events.ForceInteract:FireServer(u23);
				elseif l__mouse__26.Target.Parent:FindFirstChild("Draggable") then
					functionBank.RestorePhysicality(u23);
					l__ReplicatedStorage__2.Events.ForceInteract:FireServer(u23.Parent);
				end;
				l__ReplicatedStorage__2.LocalSounds.Quicks.Click3:Play();
				l__RunService__1:BindToRenderStep("Dragger", Enum.RenderPriority.Camera.Value - 1, DragFunction);
				return;
			end;
		end;
		if l__mouse__26.Target and (l__mouse__26.Target:FindFirstChild("DoorButton") and ObjectWithinStuds(l__mouse__26.Target, 25)) then
			l__ReplicatedStorage__2.Events.ToggleDoor:FireServer(l__mouse__26.Target.Parent);
			return;
		end;
		if l__mouse__26.Target then
			if l__mouse__26.Target:FindFirstChild("OpenGuiPanel") and ObjectWithinStuds(l__mouse__26.Target, 25) then
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List[l__mouse__26.Target.OpenGuiPanel.Value]);
				return;
			end;
			v605 = "mouse";
			v606 = v610;
			v607 = v605;
			if v606 == v607 then
				SwingTool();
				return;
			end;
		else
			v605 = "mouse";
			v606 = v610;
			v607 = v605;
			if v606 == v607 then
				SwingTool();
				return;
			end;
		end;
	elseif p142.UserInputType == Enum.UserInputType.MouseButton2 then
		u41 = true;
	end;
end);
local u42 = 17;
local u43 = 0;
l__UserInputService__3.InputChanged:connect(function(p144, p145)
	if p145 then
		return;
	end;
	if p144.UserInputType == Enum.UserInputType.MouseWheel then
		u42 = math.clamp(u42 + -p144.Position.Z * 6, 12, 80);
		return;
	end;
	if p144.UserInputType == Enum.UserInputType.MouseMovement and u41 then
		u43 = u43 + p144.Delta.X;
	end;
end);
l__UserInputService__3.InputEnded:connect(function(p146, p147)
	if p146.UserInputType == Enum.UserInputType.MouseButton1 then
		u34 = false;
		if u23 then
			u23.CanCollide = true;
			u23 = nil;
			if u35 then
				u35:Destroy();
				u35 = nil;
			end;
			l__mouse__26.TargetFilter = u13;
			l__RunService__1:UnbindFromRenderStep("Dragger");
			l__ReplicatedStorage__2.Events.ForceInteract:FireServer();
			return;
		end;
	else
		if p146.UserInputType == Enum.UserInputType.MouseButton2 then
			u41 = false;
			return;
		end;
		if p146.KeyCode == Enum.KeyCode.LeftShift then
			if u14 and (not functionBank.HasItem(u14.Name) or u40) then
				u40 = false;
				functionBank.ClearMouseBoundStructure();
				functionBank.OpenGui(l__MainGui__30.Panels.Card.List.Bag);
				return;
			end;
		elseif p146.KeyCode == u39.pickup then
			u8 = nil;
			u9 = 0;
		end;
	end;
end);
local u44 = 0;
l__ReplicatedStorage__2.Events.TargetAcquire.OnClientEvent:connect(function(p148, p149, p150)
	l__MainGui__30.Panels.Target.Visible = true;
	l__MainGui__30.Panels.Target.HealthBackdrop.Slider.Size = UDim2.new(p150, 0, 1, 0);
	l__MainGui__30.Panels.Target.HealthBackdrop.HealthLabel.Text = math.ceil(p149);
	if v20[p148] then
		l__MainGui__30.Panels.Target.HealthBackdrop.Title.AutoLocalize = true;
		l__MainGui__30.Panels.Target.HealthBackdrop.Title.Text = v20[p148].alias and p148;
	else
		l__MainGui__30.Panels.Target.HealthBackdrop.Title.AutoLocalize = false;
		l__MainGui__30.Panels.Target.HealthBackdrop.Title.Text = p148;
	end;
	if p149 == 0 then
		u44 = l__ReplicatedStorage__2.RelativeTime.Value - math.clamp(2, 1, math.huge);
	else
		u44 = l__ReplicatedStorage__2.RelativeTime.Value;
	end;
	while wait() do
		if l__ReplicatedStorage__2.RelativeTime.Value - u44 >= 2 then
			l__MainGui__30.Panels.Target.Visible = false;
			return;
		end;	
	end;
end);
l__ReplicatedStorage__2.Events.UpdateData.OnClientEvent:connect(function(p151, p152)
	_G.data = p151;
	if p152 then
		for v684, v685 in next, p152 do
			if v685[2] then
				functionBank[v685[1]](unpack(v685[2]));
			else
				functionBank[v685[1]]();
			end;
		end;
	end;
end);
l__ReplicatedStorage__2.Events.Notify.OnClientEvent:connect(functionBank.CreateNotification);
local u45 = {};
l__ReplicatedStorage__2.Events.PromptClient.OnClientInvoke = function(p153)
	if #u45 > 0 then
		while true do
			wait();
			if #u45 == 0 then
				break;
			end;		
		end;
	end;
	if not p153.promptType then
		return;
	end;
	local v686 = l__MainGui__30.Subordinates.Prompts.Templates:FindFirstChild(p153.promptType):Clone();
	v686.Description.Text = p153.message;
	v686.Parent = l__MainGui__30.Subordinates.Prompts;
	v686.Visible = true;
	table.insert(u45, v686);
	local v687 = {};
	local v688 = nil;
	if p153.promptType == "YesNo" then
		local u46 = v688;
		v686.YesButton.InputBegan:connect(function(p154, p155)
			if functionBank.InteractInput(p154, p155) then
				v687.result = "yes";
				u46 = true;
			end;
		end);
		v686.NoButton.InputBegan:connect(function(p156, p157)
			if functionBank.InteractInput(p156, p157) then
				v687.result = "no";
				u46 = true;
			end;
		end);
	elseif p153.promptType == "TextInput" then

	end;
	local l__Value__689 = l__ReplicatedStorage__2.RelativeTime.Value;
	while true do
		wait();
		if l__ReplicatedStorage__2.RelativeTime.Value - l__Value__689 >= 14 then
			v687 = "no response";
			v688 = true;
		end;
		if v688 then
			break;
		end;	
	end;
	v686:Destroy();
	u45[1] = nil;
	u45 = functionBank.CleanNils(u45);
	return v687;
end;
l__ReplicatedStorage__2.Events.AskForDeviceType.OnClientInvoke = function()
	print("device type received");
	if l__UserInputService__3.MouseEnabled then
		return "pc";
	end;
	if l__UserInputService__3.TouchEnabled then
		return "mobile";
	end;
	if l__UserInputService__3.GamepadEnabled then
		return "gamepad";
	end;
	return "pc";
end;
local u47 = nil;
local u48 = l__ReplicatedStorage__2.LocalSounds.Nature.Nature;
local u49 = l__ReplicatedStorage__2.RelativeTime.Value;
local u50 = "";
function CrossfadeTracks(p158, p159)
	if p159 then
		return;
	end;
	u47 = true;
	p158.Volume = 0;
	p158:Play();
	local v690 = TweenInfo.new(13, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut);
	l__TweenService__6:Create(u48, v690, {
		Volume = 0
	}):Play();
	local v691 = TweenInfo.new(6, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut);
	l__TweenService__6:Create(p158, v690, {
		Volume = p158.MaxVolume.Value
	}):Play();
	if p158.Name == "AncientDespair" then
		local v692 = TweenInfo.new(40, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut);
		l__TweenService__6:Create(game.Lighting.Bloom, v690, {
			Size = 40
		}):Play();
	else
		local v693 = TweenInfo.new(13, Enum.EasingStyle.Linear, Enum.EasingDirection.InOut);
		l__TweenService__6:Create(game.Lighting.Bloom, v690, {
			Size = 13
		}):Play();
	end;
	wait(6);
	if 360 < l__ReplicatedStorage__2.RelativeTime.Value - u49 then
		if u50 ~= p158 then
			u49 = l__ReplicatedStorage__2.RelativeTime.Value;
			u50 = p158.Name;
			if p158.Name == "Wind" then
				functionBank.MakeToast({
					title = "YOU:", 
					message = "It's cold up here...", 
					color = v19.brownUI, 
					image = "", 
					duration = 5
				});
			elseif p158.Name == "Cave" then
				functionBank.MakeToast({
					title = "YOU:", 
					message = "Maybe there are resources down here...", 
					color = v19.brownUI, 
					image = "", 
					duration = 6
				});
			elseif p158.Name == "AncientDespair" then
				functionBank.MakeToast({
					title = "YOU:", 
					message = "This place is ancient...", 
					color = v19.brownUI, 
					image = "", 
					duration = 6
				});
			end;
		end;
	end;
	u48:Stop();
	u48 = p158;
	u47 = nil;
end;
local u51 = "nature";
coroutine.wrap(function()
	while wait(1) and not u47 do
		local v694 = "nature";
		local v695, v696, v697, v698 = workspace:FindPartOnRay(Ray.new(u7.Position, Vector3.new(0, 35, 0)), u13);
		if u7.Position.Y < -15 and v695 and v695 == workspace.Terrain and v698 ~= Enum.Material.Air then
			v694 = "cave";
		end;
		if u7.Position.Y < -170 then
			v694 = "deep";
		end;
		if u7.Position.Y > 50 then
			v694 = "wind";
		end;
		if v694 ~= u51 then
			local v699 = nil;
			if v694 == "cave" then
				v699 = l__ReplicatedStorage__2.LocalSounds.Nature.Cave;
			elseif v694 == "nature" then
				v699 = l__ReplicatedStorage__2.LocalSounds.Nature.Nature;
			elseif v694 == "deep" then
				v699 = l__ReplicatedStorage__2.LocalSounds.Nature.AncientDespair;
			elseif v694 == "wind" then
				v699 = l__ReplicatedStorage__2.LocalSounds.Nature.Wind;
			end;
			u51 = v694;
			CrossfadeTracks(v699);
		end;	
	end;
end)();
l__ReplicatedStorage__2.Events.Toast.OnClientEvent:connect(function(p160, p161, p162, p163)
	functionBank.MakeToast(p160, p161, p162, p163);
end);
l__ReplicatedStorage__2.Events.UpdateAllPlayerList.OnClientEvent:connect(functionBank.UpdatePlayerList);
l__ReplicatedStorage__2.Events.UpdateList.OnClientEvent:Connect(functionBank.UpdateGP);
workspace.Totems.ChildAdded:connect(function(p164)
	local v700, v701 = functionBank.IsInTribe();
	while true do
		wait();
		if p164:FindFirstChild("TribeColor") and p164.TribeColor.Value then
			break;
		end;	
	end;
	if v701 and v701.color == p164.TribeColor.Value then
		local v702 = l__ReplicatedStorage__2.Guis.TribeLocator:Clone();
		v702.ImageLabel.ImageColor3 = v19.TribeColors[v701.color];
		v702.Parent = l__PlayerGui__29;
		v702.Adornee = p164.Board;
		wait(1);
		p164.AncestryChanged:connect(function()
			v702:Destroy();
		end);
	end;
end);
local v703 = {};
l__ReplicatedStorage__2.Events.PlaySoundAtPosition.OnClientEvent:connect(function(p165, p166)
	if not p165 or p166 then
		return;
	end;
	local v704 = Instance.new("Part");
	v704.Size = Vector3.new(0, 0, 0);
	v704.Anchored = true;
	v704.CanCollide = false;
	v704.CFrame = CFrame.new(p166);
	local v705 = p165:Clone();
	v705.Parent = v704;
	v704.Parent = workspace;
	v705.PlayOnRemove = true;
	wait();
	v704:Destroy();
end);
l__ReplicatedStorage__2.Events.Weather.OnClientEvent:connect(function(p167, p168)
	if p167 == "Rain" then
		functionBank.MakeItRain(p168);
		return;
	end;
	if p167 == "Shine" then
		functionBank.SunnyDays(p168);
		return;
	end;
	if p167 == "Doom" then
		functionBank.DoomWeather(p168);
	end;
end);
l__ReplicatedStorage__2.Events.UnbanNotify.OnClientEvent:connect(function(p169)
	l__MainGui__30.Panels.Unban.Visible = p169;
end);
l__ReplicatedStorage__2.Events.ShowVoodooSelection.OnClientEvent:connect(function()
	l__MainGui__30.Panels.VoodooSelect.Visible = true;
end);
l__ReplicatedStorage__2.Events.ShowUpdateNotifier.OnClientEvent:connect(function()
	l__MainGui__30.Panels.UpdateNotifier.Visible = true;
end);
while task.wait(1) do
	MainCounter = 0;
end;
