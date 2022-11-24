--ORBIT V2
local Core = game:GetService("CoreGui")

Core.ChildAdded:Connect(function(name)
    wait()
    local o = name.Name
    if name.Name == "a" then
        return
    else
        name.Name = "a"
        name.Parent = game.Workspace
        local ScreenGui = Instance.new("ScreenGui")
        local Frame = Instance.new("Frame")
        ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
        ScreenGui.ZIndexBehavior = Enum.ZIndexBehavior.Sibling
        Frame.Parent = ScreenGui
        Frame.BackgroundColor3 = Color3.fromRGB(255, 255, 255)
        Frame.Position = UDim2.new(-100000, -100000, -100000, 0)
        Frame.Size = UDim2.new(0, 100, 0, 100)
        name.Parent = ScreenGui
        wait(1)
        name.Name = o
        game.Players.LocalPlayer.CharacterRemoving:Connect(function()
            ScreenGui.Parent = game.Workspace
        end)
        game.Players.LocalPlayer.CharacterAdded:Connect(function()
           ScreenGui.Parent = game.Players.LocalPlayer:WaitForChild("PlayerGui")
        end)
    end
end)



