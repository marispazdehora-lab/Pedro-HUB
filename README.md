-- LocalScript
-- Coloque em StarterPlayerScripts

local player = game.Players.LocalPlayer

-- GUI
local gui = Instance.new("ScreenGui")
gui.Name = "PedroHub"
gui.Parent = player.PlayerGui

-- Frame Principal
local main = Instance.new("Frame")
main.Parent = gui
main.Size = UDim2.new(0,600,0,350)
main.Position = UDim2.new(0.5,-300,0.5,-175)
main.BackgroundColor3 = Color3.fromRGB(18,18,18)
main.BorderSizePixel = 0

local corner = Instance.new("UICorner", main)
corner.CornerRadius = UDim.new(0,10)

-- Barra Superior
local top = Instance.new("Frame")
top.Parent = main
top.Size = UDim2.new(1,0,0,40)
top.BackgroundColor3 = Color3.fromRGB(25,25,25)
top.BorderSizePixel = 0

local topCorner = Instance.new("UICorner", top)
topCorner.CornerRadius = UDim.new(0,10)

-- Título
local title = Instance.new("TextLabel")
title.Parent = top
title.Size = UDim2.new(0,250,1,0)
title.Position = UDim2.new(0,15,0,0)
title.BackgroundTransparency = 1
title.Text = "Pedro Hub | Blox Fruits"
title.TextColor3 = Color3.new(1,1,1)
title.TextScaled = true
title.Font = Enum.Font.GothamBold

-- Botão Fechar
local close = Instance.new("TextButton")
close.Parent = top
close.Size = UDim2.new(0,30,0,30)
close.Position = UDim2.new(1,-40,0.5,-15)
close.Text = "X"
close.TextColor3 = Color3.new(1,1,1)
close.BackgroundColor3 = Color3.fromRGB(170,0,0)
close.Font = Enum.Font.GothamBold

local closeCorner = Instance.new("UICorner", close)
closeCorner.CornerRadius = UDim.new(0,6)

close.MouseButton1Click:Connect(function()
	gui:Destroy()
end)

-- Menu lateral
local sidebar = Instance.new("Frame")
sidebar.Parent = main
sidebar.Size = UDim2.new(0,150,1,-40)
sidebar.Position = UDim2.new(0,0,0,40)
sidebar.BackgroundColor3 = Color3.fromRGB(22,22,22)
sidebar.BorderSizePixel = 0

-- Área dos botões
local content = Instance.new("Frame")
content.Parent = main
content.Size = UDim2.new(1,-160,1,-50)
content.Position = UDim2.new(0,155,0,45)
content.BackgroundTransparency = 1

-- Layout automático
local layout = Instance.new("UIListLayout")
layout.Parent = content
layout.Padding = UDim.new(0,10)

-- Criador de Botões
local function createButton(name)

	local btn = Instance.new("TextButton")
	btn.Parent = content
	btn.Size = UDim2.new(1,0,0,40)
	btn.BackgroundColor3 = Color3.fromRGB(35,35,35)
	btn.TextColor3 = Color3.new(1,1,1)
	btn.Text = name
	btn.Font = Enum.Font.Gotham
	btn.TextScaled = true
	
	local btnCorner = Instance.new("UICorner", btn)
	btnCorner.CornerRadius = UDim.new(0,6)

	btn.MouseButton1Click:Connect(function()
		print(name .. " clicado")
	end)

end

-- Botões principais
createButton("Auto Farm Level")
createButton("Teleport Island")
createButton("Auto Race V4")
createButton("ESP Players")
createButton("Auto Chest")
createButton("Fast Attack")
createButton("Boss Farm")
createButton("Auto Quest")
createButton("Auto Haki")

-- Botões do menu lateral
local function createTab(name,y)

	local tab = Instance.new("TextButton")
	tab.Parent = sidebar
	tab.Size = UDim2.new(1,-10,0,35)
	tab.Position = UDim2.new(0,5,0,y)
	tab.BackgroundColor3 = Color3.fromRGB(30,30,30)
	tab.Text = name
	tab.TextColor3 = Color3.new(1,1,1)
	tab.Font = Enum.Font.Gotham
	tab.TextScaled = true

	local tabCorner = Instance.new("UICorner", tab)
	tabCorner.CornerRadius = UDim.new(0,6)

end

createTab("Farm",10)
createTab("Teleport",55)
createTab("Visual",100)
createTab("Stats",145)
createTab("Shop",190)
createTab("Misc",235)
