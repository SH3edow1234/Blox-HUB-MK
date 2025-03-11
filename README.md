-- Painel personalizado
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = game.Players.LocalPlayer.PlayerGui

local mainFrame = Instance.new("Frame")
mainFrame.Parent = screenGui
mainFrame.Size = UDim2.new(0, 300, 0, 400)
mainFrame.Position = UDim2.new(0.05, 0, 0.05, 0)
mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
mainFrame.BorderColor3 = Color3.new(1, 0, 0)
mainFrame.BorderSizePixel = 2

-- Estampa de raio vermelho
local decal = Instance.new("Decal")
decal.Parent = mainFrame
decal.Texture = "rbxassetid://YOUR_DECAL_ID_HERE" -- Substitua pelo seu ID de decalque
decal.Face = Enum.NormalId.Front
decal.Size = Vector3.new(1, 1, 1)

-- Variáveis de estado
local teleportEnabled = false
local flyEnabled = false
local autoFarmEnabled = false
local autoFarmChestEnabled = false
local autoFarmLevelEnabled = false
local autoRaidEnabled = false
local autoFruitEnabled = false

-- Funções de ativação/desativação
local function toggleTeleport()
    teleportEnabled = not teleportEnabled
    if teleportEnabled then
        teleportButton.Text = "Teleporte: Ligado"
    else
        teleportButton.Text = "Teleporte: Desligado"
    end
end

local function toggleFly()
    flyEnabled = not flyEnabled
    if flyEnabled then
        flyButton.Text = "Voar: Ligado"
    else
        flyButton.Text = "Voar: Desligado"
    end
end

local function toggleAutoFarm()
    autoFarmEnabled = not autoFarmEnabled
    if autoFarmEnabled then
        autoFarmButton.Text = "Auto Farm: Ligado"
        startAutoFarm()
    else
        autoFarmButton.Text = "Auto Farm: Desligado"
        stopAutoFarm()
    end
end

local function toggleAutoFarmChest()
    autoFarmChestEnabled = not autoFarmChestEnabled
    if autoFarmChestEnabled then
        autoFarmChestButton.Text = "Auto Baú: Ligado"
        startAutoFarmChest()
    else
        autoFarmChestButton.Text = "Auto Baú: Desligado"
        stopAutoFarmChest()
    end
end

local function toggleAutoFarmLevel()
    autoFarmLevelEnabled = not autoFarmLevelEnabled
    if autoFarmLevelEnabled then
        autoFarmLevelButton.Text = "Auto Nível: Ligado"
        startAutoFarmLevel()
    else
        autoFarmLevelButton.Text = "Auto Nível: Desligado"
        stopAutoFarmLevel()
    end
end

local function toggleAutoRaid()
    autoRaidEnabled = not autoRaidEnabled
    if autoRaidEnabled then
        autoRaidButton.Text = "Auto Raid: Ligado"
        startAutoRaid()
    else
        autoRaidButton.Text = "Auto Raid: Desligado"
        stopAutoRaid()
    end
end

local function toggleAutoFruit()
    autoFruitEnabled = not autoFruitEnabled
    if autoFruitEnabled then
        autoFruitButton.Text = "Auto Fruta: Ligado"
        startAutoFruit()
    else
        autoFruitButton.Text = "Auto Fruta: Desligado"
        stopAutoFruit()
    end
end

-- Funções de teletransporte e voo (mantidas do script anterior)
local function teleportToRandomIsland()
    if teleportEnabled then
        -- ... (código de teletransporte para ilha aleatória)
        print("Teletransportando para ilha aleatória...")
    end
end

local function enableFlyMode()
    -- ... (código de voo)
    print("Modo de voo ativado.")
end

local function disableFlyMode()
    -- ... (código de não voo)
    print("Modo de voo desativado.")
end

-- Funções de autofarm (exemplos básicos)
local function startAutoFarm()
    -- ... (código para atacar NPCs automaticamente)
    print("Auto farm iniciado.")
end

local function stopAutoFarm()
    -- ... (código para parar o autofarm)
    print("Auto farm parado.")
end

local function startAutoFarmChest()
    -- ... (código para coletar baús automaticamente)
    print("Auto farm de baú iniciado.")
end

local function stopAutoFarmChest()
    -- ... (código para parar o autofarm de baú)
    print("Auto farm de baú parado.")
end

local function startAutoFarmLevel()
    -- ... (código para farmar nível automaticamente)
    print("Auto farm de nível iniciado.")
end

local function stopAutoFarmLevel()
    -- ... (código para parar o autofarm de nível)
    print("Auto farm de nível parado.")
end

local function startAutoRaid()
    -- ... (código para iniciar raids automaticamente)
    print("Auto raid iniciado.")
end

local function stopAutoRaid()
    -- ... (código para parar o auto raid)
    print("Auto raid parado.")
end

local function startAutoFruit()
    -- ... (código para pegar frutas automaticamente)
    print("Auto fruta iniciado.")
end

local function stopAutoFruit()
    -- ... (código para parar o auto fruta)
    print("Auto fruta parado.")
end

-- Botões
local teleportButton = Instance.new("TextButton")
teleportButton.Parent = mainFrame
teleportButton.Position = UDim2.new(0.1, 0, 0.1, 0)
teleportButton.Size = UDim2.new(0, 200, 0, 30)
teleportButton.Text = "Teleporte: Desligado"
teleportButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
teleportButton.TextColor3 = Color3.new(1, 1, 1)
teleportButton.MouseButton1Click:Connect(toggleTeleport)
teleportButton.MouseButton1Click:Connect(teleportToRandomIsland)

local flyButton = Instance.new("TextButton")
flyButton.Parent = mainFrame
flyButton.Position = UDim2.new(0.1, 0, 0.2, 0)
flyButton.Size = UDim2.new(0, 200, 0, 30)
flyButton.Text = "Voar: Desligado"
flyButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
flyButton.TextColor3 = Color3.new(1, 1, 1)
flyButton.MouseButton1Click:Connect(toggleFly)

local autoFarmButton = Instance.new("TextButton")
autoFarmButton.Parent = mainFrame
autoFarmButton.Position = UDim2.new(0.1, 0, 0.3, 0)
autoFarmButton.Size = UDim2.new(0, 200, 0, 30)
autoFarmButton.Text = "Auto Farm: Desligado"
autoFarmButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
autoFarmButton.TextColor3 = Color3.new(1, 1, 1)
autoFarmButton.MouseButton1Click:Connect(toggleAutoFarm)

local autoFarmChestButton = Instance.new("TextButton")
autoFarmChestButton.Parent = mainFrame
autoFarmChestButton.Position = UDim2.new(0.1, 0, 0.4, 0)
autoFarmChestButton.Size = UDim2.new(0, 200, 0, 30)
autoFarmChestButton.Text = "Auto Baú: Desligado"
autoFarmChestButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
autoFarmChestButton.TextColor3 = Color3.new(1, 1, 1)
autoFarmChestButton.MouseButton1Click:Connect(toggleAutoFarmChest)

local autoFarmLevelButton = Instance.new("TextButton")
autoFarmLevelButton.Parent = mainFrame
autoFarmLevelButton.Position = UDim2.new(0.1, 0, 0.5, 0)
autoFarmLevelButton.Size = UDim
