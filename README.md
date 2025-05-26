local Rayfield = loadstring(game:HttpGet('https://sirius.menu/rayfield'))()
local Window = Rayfield:CreateWindow({
   Name = "Rayfield Example Window",
   Icon = 0, -- Icon in Topbar. Can use Lucide Icons (string) or Roblox Image (number). 0 to use no icon (default).
   LoadingTitle = "minatoz hub V1",
   LoadingSubtitle = "by minato",
   Theme = "AmberGlow", -- Check https://docs.sirius.menu/rayfield/configuration/themes

   ToggleUIKeybind = "K" -- The keybind to toggle the UI visibility (string like "K" or Enum.KeyCode)

   DisableRayfieldPrompts = false,
   DisableBuildWarnings = false, -- Prevents Rayfield from warning when the script has a version mismatch with the interface

   ConfigurationSaving = {
      Enabled = true,
      FolderName = nil, -- Create a custom folder for your hub/game
      FileName = "minatohub.txt"
   },

   Discord = {
      Enabled = true, -- Prompt the user to join your Discord server if their executor supports it
      Invite = "https://discord.gg/cJyTgnWJ", -- The Discord invite code, do not include discord.gg/. E.g. discord.gg/ ABCD would be ABCD
      RememberJoins = true -- Set this to false to make them join the discord every time they load it up
   },

    ("hKeySystem = true, -- Set this to true to use our key system
   KeySettings = {
      Title = "Untitled",
      Subtitle = "Key System",
      Note = "entre no discord para conseguir a key https://discord.gg/cJyTgnWJ", -- Use this to tell the user how to get a key
      FileName = "Key", -- It is recommended to use something unique as other scripts using Rayfield may overwrite your key file
      SaveKey = true, -- The user's key will be saved, but if you change the key, they will be unable to use your script
      GrabKeyFromSite = false, -- If this is true, set Key below to the RAW site you would like Rayfield to get the key from
      Key = {"minatohubv1"} -- List of keys that will be accepted by the system, can be RAW file links (pastebin, github etc) or simple stringsello","key22")
   }
})
local Tab = Window:CreateTab("troll", 6180316273) -- Title, Image

local Toggle = Tab:CreateToggle({
   Name = "Toggle Example",
   CurrentValue = false,
   Flag = "auto parry", -- A flag is the identifier for the configuration file, make sure every element has a different flag if you're using configuration saving to ensure no overlaps
   Callback = function(Value)
   getgenv().god = true
while getgenv().god and task.wait() do
    for _, ball in next, workspace.Balls:GetChildren() do
        if ball then
            local player = game:GetService("Players").LocalPlayer
            local character = player.Character
            if character and character:FindFirstChild("HumanoidRootPart") then
                character.HumanoidRootPart.CFrame = CFrame.new(character.HumanoidRootPart.Position, ball.Position)
                if character:FindFirstChild("Highlight") then
                    character.HumanoidRootPart.CFrame = ball.CFrame * CFrame.new(0, 0, ball.Velocity.Magnitude * -0.5)
                    game:GetService("ReplicatedStorage").Remotes.ParryButtonPress:Fire()
                end
            end
        end
    end
end

   end,
})
