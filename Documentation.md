## EasyFunction Documentation
EasyFunction is a custom module for roblox to make ur life easier when scripting.

## Using the module
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
```
## Creating a highlight esp
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
FuncLib.Visuals:HighlightEsp('Builderman',Color3.new(8, 255, 241)) -- u can change the builderman to other player name
```
## Creating a highlight esp to all players
```lua
local FuncLib = loadstring(game:HttpGet('https://raw.githubusercontent.com/ScriptSkiddie69/EasyFunction/main/Source'))()
for i,v in pairs(game.Players:GetPlayers()) -- gets all player
if v.Character then
FuncLib.Visuals:HighlightEsp(v.Name,Color3.new(8, 255, 241)) -- u can change the builderman to other player name
end
end
```
