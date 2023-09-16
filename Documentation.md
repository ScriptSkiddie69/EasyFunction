## EasyFunction Documentation
EasyFunction is a custom module for roblox to make ur life easier when scripting.

## Using the module
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
```
## Creating a highlight esp
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Visuals:HighlightEsp('PlayerName',Color3.new(8, 255, 241)) -- u can change the PlayerName to other player name
```
## Creating a highlight esp to all players
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
for i,v in pairs(game.Players:GetPlayers()) do -- gets all player
if v.Character and v.Name ~= game.Players.LocalPlayer.Name then -- check if the player have a character and is not yourself
FuncLib.Visuals:HighlightEsp(v.Name,Color3.new(8, 255, 241)) -- creates a highlight esp
   end
end
```
## Disabling the highlight esp 
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Visuals:DisableEsp('PlayerName') -- disable the esp to a specific player 
```
## Disabling the highlight esp to all players
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
for i,v in pairs(game.Players:GetPlayers()) do -- gets all player
if v.Character and v.Name ~= game.Players.LocalPlayer.Name then -- checks if the player have a character and is not yourself
FuncLib.Visuals:DisableEsp(v.Name) -- disables the esp to all player
   end
end
```
## Teleporting to a player
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:Teleport('PlayerName') -- teleports to a player named playername
```

## Printing the nearest player
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
print(FuncLib.Check:GetNearestPlayer()) -- prints the nearest player on you
```

## Teleporting to the nearest player
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:Teleport(FuncLib.Check:GetNearestPlayer())
```
## Example on making a killaura script using the nearest player function
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

local args = {
    player = FuncLib.Check:GetNearestPlayer()
}
game.ReplicatedStorage.Remotes.KillRemote:FireServer(unpack(args)) -- Note this does not work on any game as it is just an example
```
## Setting walkspeed value to a different one
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:SetWalkSpeed(120) -- whatever u wanna set ur walkspeed to
```
## Setting jumppower value to a different one
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:SetJumpPower(120) -- whatever u wanna set ur jumppower to
```
## Making a teleport aura loop function
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
function tpaura()
FuncLib.Functions:Teleport(FuncLib.Check:GetNearestPlayer())
end
-- FuncLib.Functions:SetLoop(Delay, bool, loopname, Function) -- This is what it looks like
FuncLib.Functions:SetLoop(1, true, "ThisShouldBeRandomOnEveryLoop", tpaura) -- this will repeatedly teleports to the nearest player
```
## Disabling the same loop 
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:SetLoop(1, false, "ThisShouldBeRandomOnEveryLoop", FuncLib.Functions:Teleport(FuncLib.Check:GetNearestPlayer()))
```

## Getting all properties
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
-- Example we have a part called ball
for property,value in pairs(FuncLib.Functions:GetProperties(game.Workspace.Ball)) do
    print(property,value) -- this will return the property and the value
    print(property) -- this will return only the property 
end
```
it should be the same loopname if u wanna enable/disable it if its something else it will do nothing

## Hooking properties value
it uses hookfunction and it looks like this FuncLib.Functions:HookValue(object,properties,value)
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:HookValue('Humanoid','WalkSpeed',1200)
game.Players.LocalPlayer.Character.Humanoid.WalkSpeed = 69
print(game.Players.LocalPlayer.Character.Humanoid.WalkSpeed)
-- this should return 69 but we hooked the value so it returns 1200 tho in reality the walkspeed is 69
-- youll stil walk at 69 walkspeed instead of 1200
```

## Hooking all of the properties at once
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
-- We will need to use the getproperties() function at the above ive explained
-- example were hooking ur humanoid properties
local humanoid = game.Players.LocalPlayer.Character.Humanoid

-- Now we will need to make a for loop so we can use the getproperties() function

for property,value in pairs(FuncLib.Functions:GetProperties(humanoid)) do -- this is how to use the getproperties function now dont forget the instance at the above
FuncLib.Functions:HookValue(humanoid,property,1200)-- heres the fun stuff we will hook every properties the humanoid have we will need to use humanoid for the first argument, we will need to use property for the second argument, for the third any value u want, now we've successfuly hooked the property and value nice!
end
```

## AntiKick function However this isnt very effective allthough u can try

```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Functions:AntiKick("hook") -- all methods: remote, hook
```

## Checking if property exists

```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

--FuncLib.Functions:CheckProperty(instance,property)
-- the instance MUST BE an instance not string or else it wont do nothing.
if FuncLib.Functions:CheckProperty(game.Players.LocalPlayer.Character.HumanoidRootPart,"CFrame") then -- returns true if the instance has that property
print('property exists!')
end
```

## Checking if an instance is destroyed

```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

FuncLib.Functions:IsPartDestroyed({
    part = "game.Workspace.Part",
    connection = "wtf", -- ignore connection for now we'll get to that later
    callback = function(t)
        print(t) -- This will print true or false based on whether the part is destroyed or not
      --PUT UR CODE HERE IT WILL ONLY RUN IF game.Workspace.Part is destroyed
    end
})
```
## Checking if a child of an instance is added

```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

Custom.Functions:ChildAdded({
    instance = game.Players.LocalPlayer.Character,
    connection = "abcd", -- Lets ignore the connection for now, we'll get into that later
    callback = function(t)
        print(t) -- will print the child that added example basepart added to the instance
       -- PUT UR CODE HERE IT WILL ONLY RUN IF a child is added on game.Players.LocalPlayer.Character or the instance uve put
    end
})
```

## Checking if a descendant of an instance is added

```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

Custom.Functions:DescendantAdded({
    instance = game.Players.LocalPlayer.Character,
    connection = "abcd", -- ignore connection for now we'll get into that later
    callback = function(t)
        print(t) -- Will print whenever a descendant is added
         -- PUT YOUR CODE HERE IT WILL ONLY RUN if a descendant is added on game.Players.LocalPlayer.Character or in the instance uve put
end
})

```

## Disconnecting a connection or a function uve ran 
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()

-- Example youve ran descendantadded function

Custom.Functions:DescendantAdded({
    instance = game.Players.LocalPlayer.Character,
    connection = "abcd", -- ignore connection for now we'll get into that later
    callback = function(t)
        print(t) -- Will print whenever a descendant is added
         -- PUT YOUR CODE HERE IT WILL ONLY RUN if a descendant is added on game.Players.LocalPlayer.Character or in the instance uve put
end

-- Now what we're gonna do is get the connection of that DescendantAdded, its abcd right?, okay now we're gonna disconnect it so it wont run

Custom.Functions:Disconnect('abcd') -- disconnects the function
```
