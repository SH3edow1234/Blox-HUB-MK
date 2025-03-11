-- Painel personalizado
local screenGui = Instance.new("ScreenGui")
screenGui.Parent = game.Players.LocalPlayer.PlayerGui

local mainFrame = Instance.new("Frame")
mainFrame.Parent = screenGui
mainFrame.Size = UDim2.new(0, 300, 0, 200)
mainFrame.Position = UDim2.new(0.05, 0, 0.05, 0)
mainFrame.BackgroundColor3 = Color3.new(0, 0, 0) -- Fundo preto
mainFrame.BorderColor3 = Color3.new(1, 0, 0) -- Borda vermelha
mainFrame.BorderSizePixel = 2

-- Estampa de raio vermelho (substitua pelo seu ID de decalque)
local decal = Instance.new("Decal")
decal.Parent = mainFrame
decal.Texture = "rbxassetid://YOUR_DECAL_ID_HERE" -- Substitua pelo ID do seu decalque de raio
decal.Face = Enum.NormalId.Front
decal.Size = Vector3.new(1, 1, 1)

-- Variáveis de estado
local teleportEnabled = false
local flyEnabled = false

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
    enableFlyMode()
  else
    flyButton.Text = "Voar: Desligado"
    disableFlyMode()
  end
end

-- Funções de teletransporte e voo (mantidas do script anterior)
local function teleportToRandomIsland()
  if teleportEnabled then
    -- ... (código de teletransporte)
  end
end

local function enableFlyMode()
  -- ... (código de voo)
end

local function disableFlyMode()
  -- ... (código de não voo)
end

-- Botões
local teleportButton = Instance.new("TextButton")
teleportButton.Parent = mainFrame
teleportButton.Position = UDim2.new(0.1, 0, 0.1, 0)
teleportButton.Size = UDim2.new(0, 200, 0, 40)
teleportButton.Text = "Teleporte: Desligado"
teleportButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
teleportButton.TextColor3 = Color3.new(1, 1, 1)
teleportButton.MouseButton1Click:Connect(toggleTeleport)

local flyButton = Instance.new("TextButton")
flyButton.Parent = mainFrame
flyButton.Position = UDim2.new(0.1, 0, 0.3, 0)
flyButton.Size = UDim2.new(0, 200, 0, 40)
flyButton.Text = "Voar: Desligado"
flyButton.BackgroundColor3 = Color3.new(0.2, 0.2, 0.2)
flyButton.TextColor3 = Color3.new(1, 1, 1)
flyButton.MouseButton1Click:Connect(toggleFly)

-- Loop para teletransporte automático (opcional)
while wait(5) do
  teleportToRandomIsland()
end
