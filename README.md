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
