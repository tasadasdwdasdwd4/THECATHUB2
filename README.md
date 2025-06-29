loadstring(game:HttpGet(("https://raw.githubusercontent.com/daucobonhi/Scriptfly/refs/heads/main/vietnam.lua")))()

       local Window = MakeWindow({
         Hub = {
         Title = "TY_THECAT",
         Animation = "Youtube: TY_THECAT"
         },
        Key = {
        KeySystem = false,
        Title = "Key IS THECAT",
        Description = "",
        KeyLink = "",
        Keys = {"THECAT"},
        Notifi = {
        Notifications = true,
        CorrectKey = "Running the Script...",
       Incorrectkey = "The key is incorrect",
       CopyKeyLink = "Copied to Clipboard"
      }
    }
  })

       MinimizeButton({
       Image = "http://www.roblox.com/asset/?id=83190276951914",
       Size = {60, 60},
       Color = Color3.fromRGB(10, 10, 10),
       Corner = true,
       Stroke = false,
       StrokeColor = Color3.fromRGB(255, 0, 0)
      })
      
Name: PlayerNameBox
Class: TextBox
PlaceholderText: "Name Player"
Size: UDim2.new(0.8, 0, 0, 60)
Position: UDim2.new(0.1, 0, 0, 80)
TextScaled: true
BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextColor3 = Color3.new(0, 0, 0)

Name: KillButton
Class: TextButton
Text: "enter kill"
Size: UDim2.new(0.8, 0, 0, 60)
Position: UDim2.new(0.1, 0, 0, 400)
BackgroundColor3 = Color3.fromRGB(255, 255, 255)
TextColor3 = Color3.new(0, 0, 0)
TextScaled = true

local ReplicatedStorage = game:GetService("ReplicatedStorage")
local killEvent = ReplicatedStorage:WaitForChild("KillPlayerEvent")

killEvent.OnServerEvent:Connect(function(player, targetPlayer)
	if targetPlayer and targetPlayer.Character and targetPlayer.Character:FindFirstChild("Humanoid") then
		targetPlayer.Character.Humanoid.Health = 0
	end
end)
