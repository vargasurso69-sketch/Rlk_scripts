-- Script de Teste - Versão Simples
-- Este script demonstra conceitos básicos de Lua no Roblox

local player = game.Players.LocalPlayer
local character = player.Character or player.CharacterAdded:Wait()
local humanoidRootPart = character:WaitForChild("HumanoidRootPart")

-- Função para imprimir mensagens
local function print_message(message)
    print("[Script] " .. message)
end

print_message("Script iniciado!")

-- Função para mover o personagem
local function move_player(x, y, z)
    humanoidRootPart.CFrame = CFrame.new(x, y, z)
    print_message("Jogador movido para: " .. x .. ", " .. y .. ", " .. z)
end

-- Função para dar informações do jogador
local function show_player_info()
    print_message("Jogador: " .. player.Name)
    print_message("Posição: " .. tostring(humanoidRootPart.Position))
    print_message("Saúde: " .. character:WaitForChild("Humanoid").Health)
end

-- Exemplo de uso
show_player_info()
wait(2)

-- Move o jogador 10 studs para a direita
move_player(humanoidRootPart.Position.X + 10, humanoidRootPart.Position.Y, humanoidRootPart.Position.Z)

print_message("Script finalizado!")