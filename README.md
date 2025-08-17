-- GUI Toggle para 99 Noites na Floresta
-- Criado para o jogador: Fredsxx — Compatível com KRNL / Synapse etc.

local Rayfield = loadstring(game:HttpGet('https://raw.githubusercontent.com/shlexware/Rayfield/main/source'))()

local Window = Rayfield:CreateWindow({
    Name = "Fredsxx - 99 Noites na Floresta",
    LoadingTitle = "Carregando...",
    LoadingSubtitle = "Boa sorte na sobrevivência!",
    ConfigurationSaving = { Enabled = false },
    Discord = { Enabled = false },
    KeySystem = false
})

-- Botão de exemplo: Teleport para posição estratégia fictícia
local function TeleportSafeZone()
    local plr = game:GetService("Players").LocalPlayer
    if plr.Character and plr.Character:FindFirstChild("HumanoidRootPart") then
        -- Valor de CFrame fictício, ajuste conforme necessidade
        plr.Character.HumanoidRootPart.CFrame = CFrame.new(0, 10, 0)
    end
end

-- Aba de Ações
local MainTab = Window:CreateTab(" Ações", nil)

MainTab:CreateButton({
    Name = " Teleportar para Zona Segura",
    Callback = TeleportSafeZone
})

-- Botão para esconder/exibir a GUI
MainTab:CreateButton({
    Name = "  Toggle GUI (Esconder/Mostrar)",
    Callback = function()
        local gui = game:GetService("CoreGui"):FindFirstChild("Rayfield")
        if gui then
            gui.Enabled = not gui.Enabled
        end
    end,
})

-- Notificação inicial personalizada
Rayfield:Notify({
    Title = " GUI Ativada!",
    Content = "Boa sorte nas 99 Noites, Fredsxx!",
    Duration = 5
})
