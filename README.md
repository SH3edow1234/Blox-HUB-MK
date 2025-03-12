-- Verifica se o jogador local existe
if game and game.Players and game.Players.LocalPlayer then
    local player = game.Players.LocalPlayer
    local playerGui = player:WaitForChild("PlayerGui")

    -- Painel personalizado
    local screenGui = Instance.new("ScreenGui")
    screenGui.Parent = playerGui

    local mainFrame = Instance.new("Frame")
    mainFrame.Parent = screenGui
    mainFrame.Size = UDim2.new(0, 300, 0, 400)
    mainFrame.Position = UDim2.new(0.05, 0, 0.05, 0)
    mainFrame.BackgroundColor3 = Color3.new(0, 0, 0)
    mainFrame.BorderColor3 = Color3.new(1, 0, 0)
    mainFrame.BorderSizePixel = 2

    -- Imagem de fundo neon vermelha
    local backgroundImage = Instance.new("ImageLabel")
    backgroundImage.Parent = mainFrame
    backgroundImage.Size = UDim2.new(1, 0, 1, 0)
    backgroundImage.BackgroundTransparency = 1
    backgroundImage.Image = "rbxassetid://YOUR_NEON_RED_IMAGE_ID_HERE" -- Substitua pelo seu ID de imagem
    backgroundImage.ZIndex = 0

    -- Título
    local titleLabel = Instance.new("TextLabel")
    titleLabel.Parent = mainFrame
    titleLabel.Size = UDim2.new(1, 0, 0, 30)
    titleLabel.Position = UDim2.new(0, 0, 0, 0)
    titleLabel.BackgroundTransparency = 1
    titleLabel.Text = "Painel de Hacks"
    titleLabel.TextColor3 = Color3.new(1, 0, 0)
    titleLabel.Font = Enum.Font.SciFi
    titleLabel.TextScaled = true

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
            teleportButton.Text = "Teleporte: Ligado (Teleporta para ilha aleatória)"
        else
            teleportButton.Text = "Teleporte: Desligado"
        end
    end

    local function toggleFly()
        flyEnabled = not flyEnabled
        if flyEnabled then
            flyButton.Text = "Voar: Ligado (Permite voar)"
            enableFlyMode()
        else
            flyButton.Text = "Voar: Desligado"
            disableFlyMode()
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
            autoFarmChestButton.Text = "Auto Farm Baú: Ligado"
            startAutoFarmChest()
        else
            autoFarmChestButton.Text = "Auto Farm Baú: Desligado"
            stopAutoFarmChest()
        end
    end

    local function toggleAutoFarmLevel()
        autoFarmLevelEnabled = not autoFarmLevelEnabled
        if autoFarmLevelEnabled then
            autoFarmLevelButton.Text = "Auto Farm Nível: Ligado"
            startAutoFarmLevel()
        else
            autoFarmLevelButton.Text = "Auto Farm Nível: Desligado"
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
    local teleportButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.1, 0), "Teleporte: Desligado", function() toggleTeleport(); teleportToRandomIsland() end)
    local flyButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.2, 0), "Voar: Desligado", toggleFly)
    local autoFarmButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.3, 0), "Auto Farm: Desligado", toggleAutoFarm)
    local autoFarmChestButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.4, 0), "Auto Baú: Desligado", toggleAutoFarmChest)
    local autoFarmLevelButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.5, 0), "Auto Nível: Desligado", toggleAutoFarmLevel)
    local autoRaidButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.6, 0), "Auto Raid: Desligado", toggleAutoRaid)
    local autoFruitButton = createStyledButton(mainFrame, UDim2.new(0.1, 0, 0.7, 0), "Auto Fruta: Desligado", toggleAutoFruit)

    function createStyledButton(parent, position, text, connectFunction)
        local button = Instance.new("TextButton")
        button.Parent = parent
        button.Position = position
        button.Size = UDim2.new(0, 200,
