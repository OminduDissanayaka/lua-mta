# 🎮 Lua Programming සහ MTA:SA Resource Development

---

## 📚 පටුන

### **Part 1: Lua Programming Basics**
1. [Lua හැඳින්වීම](#1-lua-හඳනවීම)
2. [Variables සහ Data Types](#2-variables-සහ-data-types)
3. [Operators](#3-operators)
4. [Control Structures](#4-control-structures)
5. [Functions](#5-functions)
6. [Tables](#6-tables)
7. [Strings](#7-strings)
8. [Loops](#8-loops)
9. [Modules](#9-modules)
10. [Error Handling](#10-error-handling)

### **Part 2: MTA:SA Resource Development**
11. [MTA:SA හැඳින්වීම](#11-mtasa-හඳනවීම)
12. [Resource Structure](#12-resource-structure)
13. [Server-Side Scripting](#13-server-side-scripting)
14. [Client-Side Scripting](#14-client-side-scripting)
15. [Events සහ Event Handlers](#15-events-සහ-event-handlers)
16. [Elements සහ Data](#16-elements-සහ-data)
17. [GUI Development](#17-gui-development)
18. [Database Integration](#18-database-integration)
19. [Advanced Concepts](#19-advanced-concepts)
20. [Best Practices](#20-best-practices)

---

## Part 1: Lua Programming Basics

---

### 1. Lua හඳින්වීම

#### Lua කියන්නේ මොකද්ද?
Lua යනු සරල, වේගවත්, සහ powerful scripting භාෂාවක්. එය game development, embedded systems, සහ web applications වල බහුලව භාවිතා වෙනවා.

#### Lua වල විශේෂාංග:
- 🚀 **වේගවත්** - ඉතා වේගවත් execution speed එකක්
- 📦 **සරල** - ඉගෙන ගන්න ඉතා පහසු
- 🔧 **නම්‍යශීලී** - විවිධ වැඩකටයුතු වලට යොදාගන්න පුළුවන්
- 🎮 **Game Friendly** - game scripting සඳහා ඉතා සුදුසු

#### පළමු Lua Program එක:
```lua
-- මේක comment එකක්
print("Hello, World!") -- කොන්සෝලය මත output එකක් print කරනවා
```

---

### 2. Variables සහ Data Types

#### Variables කියන්නේ මොකද්ද?
Variable යනු data එකක් store කරන container එකක්. Lua වල variables declare කරන විට type එක specify කරන්න අවශ්‍ය නැහැ.

#### Variable Types:

**1. Local Variables (පෙදෙසික විචල්‍ය)**
```lua
local name = "Kasun" -- local variable එකක්
local age = 25
```

**2. Global Variables (ගෝලීය විචල්‍ය)**
```lua
playerName = "Nimal" -- global variable එකක්
score = 100
```

> ⚠️ **වැදගත්:** සෑම විටම `local` භාවිතා කරන්න, global variables memory leak වලට හේතු වෙන්න පුළුවන්.

#### Data Types (දත්ත වර්ග):

**1. nil (හිස්)**
```lua
local x = nil -- අගයක් නැති variable එකක්
print(type(x)) -- Output: nil
```

**2. boolean (සත්‍ය/අසත්‍ය)**
```lua
local isAlive = true
local isGameOver = false
```

**3. number (සංඛ්‍යා)**
```lua
local integerNum = 42
local floatNum = 3.14
local negative = -100
```

**4. string (පෙළ)**
```lua
local singleQuote = 'Hello'
local doubleQuote = "World"
local multiLine = [[මේක
multiple line
string එකක්]]
```

**5. table (වගුව)**
```lua
local fruits = {"amba", "puhul", "anoda"}
local person = {name = "Kamal", age = 30}
```

**6. function (ක්‍රියාව)**
```lua
local function greet()
    print("ආයුබෝවන්!")
end
```

#### Type Checking:
```lua
local x = 10
print(type(x)) -- Output: number

local name = "Saman"
print(type(name)) -- Output: string
```

---

### 3. Operators

#### Arithmetic Operators (ගණිතමය ක්‍රියාකරු):
```lua
local a = 10
local b = 3

print(a + b)  -- එකතු කිරීම: 13
print(a - b)  -- අඩු කිරීම: 7
print(a * b)  -- ගුණ කිරීම: 30
print(a / b)  -- බෙදීම: 3.333...
print(a % b)  -- Modulo (ඉතිරිය): 1
print(a ^ b)  -- Power (බලය): 1000
```

#### Relational Operators (සාපේක්ෂ ක්‍රියාකරු):
```lua
local x = 5
local y = 10

print(x == y)  -- සමාන: false
print(x ~= y)  -- සමාන නොවේ: true
print(x < y)   -- අඩු: true
print(x > y)   -- වැඩි: false
print(x <= y)  -- අඩු හෝ සමාන: true
print(x >= y)  -- වැඩි හෝ සමාන: false
```

#### Logical Operators (තාර්කික ක්‍රියාකරු):
```lua
local a = true
local b = false

print(a and b)  -- AND: false
print(a or b)   -- OR: true
print(not a)    -- NOT: false
```

#### String Concatenation (පෙළ එකතු කිරීම):
```lua
local firstName = "Nimal"
local lastName = "Silva"
local fullName = firstName .. " " .. lastName
print(fullName) -- Output: Nimal Silva
```

---

### 4. Control Structures

#### If-Else Statements:

**මූලික if statement:**
```lua
local age = 18

if age >= 18 then
    print("ඔබ වැඩිහිටියෙක්")
end
```

**If-Else:**
```lua
local score = 45

if score >= 50 then
    print("Pass")
else
    print("Fail")
end
```

**If-Elseif-Else:**
```lua
local marks = 75

if marks >= 75 then
    print("A Grade")
elseif marks >= 65 then
    print("B Grade")
elseif marks >= 55 then
    print("C Grade")
elseif marks >= 35 then
    print("S Grade")
else
    print("Fail")
end
```

**Nested If (කැදැලි if):**
```lua
local age = 20
local hasLicense = true

if age >= 18 then
    if hasLicense then
        print("ඔබට drive කරන්න පුළුවන්")
    else
        print("පළමුව license එකක් ගන්න")
    end
else
    print("ඔබ තවමත් අඩුයි")
end
```

---

### 5. Functions

#### Functions කියන්නේ මොකද්ද?
Function එකක් යනු නිශ්චිත කාර්යයක් කරන code block එකක්. Functions භාවිතා කරන්නේ code එක reuse කරන්න සහ organize කරන්න.

#### Basic Function:
```lua
function greet()
    print("ආයුබෝවන්!")
end

greet() -- function එක call කරනවා
```

#### Parameters සමඟ Function:
```lua
function greet(name)
    print("ආයුබෝවන් " .. name .. "!")
end

greet("කමල්")  -- Output: ආයුබෝවන් කමල්!
greet("නිමල්")  -- Output: ආයුබෝවන් නිමල්!
```

#### Multiple Parameters:
```lua
function add(a, b)
    return a + b
end

local result = add(5, 3)
print(result) -- Output: 8
```

#### Multiple Return Values:
```lua
function calculate(a, b)
    local sum = a + b
    local product = a * b
    return sum, product
end

local s, p = calculate(4, 5)
print("එකතුව: " .. s)      -- Output: එකතුව: 9
print("ගුණිතය: " .. p)    -- Output: ගුණිතය: 20
```

#### Local Functions:
```lua
local function privateFunction()
    print("මේක local function එකක්")
end

privateFunction()
```

#### Anonymous Functions (නාමරහිත ක්‍රියා):
```lua
local square = function(x)
    return x * x
end

print(square(5)) -- Output: 25
```

#### Default Parameters:
```lua
function greet(name, greeting)
    greeting = greeting or "ආයුබෝවන්" -- default value
    print(greeting .. " " .. name)
end

greet("කමල්")                    -- Output: ආයුබෝවන් කමල්
greet("නිමල්", "සුබ දවසක්")     -- Output: සුබ දවසක් නිමල්
```

---

### 6. Tables

#### Tables කියන්නේ මොකද්ද?
Table එකක් යනු Lua වල ඇති එකම data structure එක. Arrays, dictionaries, objects හැමදේම tables භාවිතයෙන් හදන්න පුළුවන්.

#### Array-Style Tables (අනුක්‍රමික වගු):
```lua
local fruits = {"amba", "puhul", "anoda", "දොඩම්"}

print(fruits[1])  -- Output: amba (Lua වල index 1 සිට පටන් ගන්නවා)
print(fruits[3])  -- Output: anoda

-- Table එකේ length එක
print(#fruits)    -- Output: 4
```

#### Dictionary-Style Tables (ශබ්දකෝෂ වගු):
```lua
local person = {
    name = "කමල්",
    age = 25,
    city = "කොළඹ"
}

print(person.name)    -- Output: කමල්
print(person["age"])  -- Output: 25
```

#### Nested Tables (කැදැලි වගු):
```lua
local school = {
    name = "රාජකීය විද්‍යාලය",
    students = {
        {name = "කමල්", age = 15},
        {name = "නිමල්", age = 16},
        {name = "සුනිල්", age = 15}
    }
}

print(school.students[1].name)  -- Output: කමල්
```

#### Table Functions (වගු ක්‍රියා):

**table.insert() - අයිතම එකතු කරනවා**
```lua
local colors = {"red", "green"}
table.insert(colors, "blue")      -- අන්තයට එකතු කරනවා
table.insert(colors, 2, "yellow") -- position 2 වලට එකතු කරනවා

-- colors = {"red", "yellow", "green", "blue"}
```

**table.remove() - අයිතම ඉවත් කරනවා**
```lua
local numbers = {10, 20, 30, 40}
table.remove(numbers, 2)  -- index 2 ඉවත් කරනවා
table.remove(numbers)     -- අන්තිම element එක ඉවත් කරනවා
```

**table.concat() - පෙළක් හදනවා**
```lua
local words = {"Hello", "World", "Lua"}
local sentence = table.concat(words, " ")
print(sentence)  -- Output: Hello World Lua
```

**table.sort() - පිළිවෙල කරනවා**
```lua
local numbers = {5, 2, 8, 1, 9}
table.sort(numbers)
-- numbers = {1, 2, 5, 8, 9}
```

#### Iterating Tables (වගු පුනරාවර්තනය):
```lua
local fruits = {"amba", "puhul", "anoda"}

-- ipairs භාවිතයෙන් (arrays සඳහා)
for index, fruit in ipairs(fruits) do
    print(index, fruit)
end

-- pairs භාවිතයෙන් (dictionaries සඳහා)
local person = {name = "කමල්", age = 25}
for key, value in pairs(person) do
    print(key, value)
end
```

---

### 7. Strings

#### String Operations:

**String Length (දිග):**
```lua
local text = "ආයුබෝවන්"
print(#text)              -- string එකේ length එක
print(string.len(text))   -- alternate method
```

**String Concatenation (එකතු කිරීම):**
```lua
local first = "Hello"
local second = "World"
local combined = first .. " " .. second
print(combined)  -- Output: Hello World
```

**Uppercase/Lowercase:**
```lua
local text = "Hello Lua"
print(string.upper(text))  -- Output: HELLO LUA
print(string.lower(text))  -- Output: hello lua
```

**Substring (උප පෙළ):**
```lua
local text = "Hello World"
print(string.sub(text, 1, 5))   -- Output: Hello
print(string.sub(text, 7))      -- Output: World
```

**Find and Replace:**
```lua
local text = "I love Lua programming"

-- Find
local start, finish = string.find(text, "Lua")
print(start, finish)  -- Output: 8 10

-- Replace
local newText = string.gsub(text, "Lua", "Python")
print(newText)  -- Output: I love Python programming
```

**String Formatting:**
```lua
local name = "කමල්"
local age = 25
local formatted = string.format("නම: %s, වයස: %d", name, age)
print(formatted)  -- Output: නම: කමල්, වයස: 25
```

**Repeat:**
```lua
local star = "*"
print(string.rep(star, 5))  -- Output: *****
```

**Reverse:**
```lua
local text = "Lua"
print(string.reverse(text))  -- Output: auL
```

---

### 8. Loops

#### For Loop:

**Numeric For Loop:**
```lua
-- 1 සිට 5 දක්වා
for i = 1, 5 do
    print(i)
end
-- Output: 1 2 3 4 5

-- Step සමඟ
for i = 0, 10, 2 do
    print(i)
end
-- Output: 0 2 4 6 8 10

-- Reverse
for i = 5, 1, -1 do
    print(i)
end
-- Output: 5 4 3 2 1
```

**Generic For Loop (Tables සඳහා):**
```lua
local fruits = {"amba", "puhul", "anoda"}

for index, fruit in ipairs(fruits) do
    print(index .. ": " .. fruit)
end
```

#### While Loop:
```lua
local count = 1

while count <= 5 do
    print("Count: " .. count)
    count = count + 1
end
```

#### Repeat-Until Loop:
```lua
local x = 1

repeat
    print(x)
    x = x + 1
until x > 5
```

#### Break and Continue:
```lua
-- Break භාවිතය
for i = 1, 10 do
    if i == 5 then
        break  -- loop එක නතර කරනවා
    end
    print(i)
end

-- Continue effect එක (Lua වල continue නැහැ)
for i = 1, 10 do
    if i % 2 == 0 then
        goto continue  -- skip කරනවා
    end
    print(i)
    ::continue::
end
```

---

### 9. Modules

#### Modules කියන්නේ මොකද්ද?
Module එකක් යනු reusable code එකක් තියෙන separate file එකක්.

#### Module එකක් හදන්නේ කොහොමද:

**mymodule.lua:**
```lua
local M = {}  -- Module table එක

M.version = "1.0"

function M.greet(name)
    return "ආයුබෝවන් " .. name
end

function M.add(a, b)
    return a + b
end

return M
```

#### Module එකක් භාවිතා කරන්නේ කොහොමද:
```lua
local mymodule = require("mymodule")

print(mymodule.version)           -- Output: 1.0
print(mymodule.greet("කමල්"))     -- Output: ආයුබෝවන් කමල්
print(mymodule.add(5, 3))         -- Output: 8
```

---

### 10. Error Handling

#### pcall (Protected Call):
```lua
local function riskyFunction()
    error("මෙහි දෝෂයක් සිදු විය!")
end

local success, errorMessage = pcall(riskyFunction)

if success then
    print("සාර්ථකයි!")
else
    print("දෝෂය: " .. errorMessage)
end
```

#### xpcall (Extended Protected Call):
```lua
local function errorHandler(err)
    return "දෝෂ හසුරුවන්නා: " .. err
end

local function riskyFunction()
    local x = nil
    return x.value  -- මෙහි error එකක් ඇති වෙනවා
end

local success, result = xpcall(riskyFunction, errorHandler)
print(result)
```

#### assert භාවිතය:
```lua
local function divide(a, b)
    assert(b ~= 0, "ශුන්‍යයෙන් බෙදිය නොහැක!")
    return a / b
end

print(divide(10, 2))  -- Output: 5
-- print(divide(10, 0))  -- Error: ශුන්‍යයෙන් බෙදිය නොහැක!
```

---

## Part 2: MTA:SA Resource Development

---

### 11. MTA:SA හඳින්වීම

#### MTA:SA කියන්නේ මොකද්ද?
Multi Theft Auto: San Andreas (MTA:SA) යනු GTA San Andreas game එක සඳහා multiplayer mod එකක්. මෙහි Lua භාවිතයෙන් custom game modes හදන්න පුළුවන්.

#### MTA:SA වල ප්‍රධාන සංකල්ප:

**1. Server සහ Client:**
- **Server-Side**: සර්වරයේ run වෙන scripts (ක්‍රීඩකයින්ට බලන්න බැහැ)
- **Client-Side**: ක්‍රීඩකයාගේ computer එකේ run වෙන scripts

**2. Resources:**
Resource එකක් යනු game mode එකක්, script එකක්, හෝ feature එකක්. එක එක resource වලට තමන්ගේම folder එකක් තියෙනවා.

**3. Elements:**
MTA වල හැම දෙයක්ම (players, vehicles, objects) "elements" ලෙස හැඳින්වෙනවා.

---

### 12. Resource Structure

#### Resource Folder Structure:
```
myresource/
│
├── meta.xml          (Resource configuration file)
├── server.lua        (Server-side script)
├── client.lua        (Client-side script)
├── shared.lua        (දෙපැත්තටම access වෙන script)
│
├── images/           (Images folder)
│   └── logo.png
│
├── sounds/           (Sounds folder)
│   └── notification.mp3
│
└── data/            (Data folder)
    └── config.lua
```

#### meta.xml File:

**මූලික meta.xml:**
```xml
<meta>
    <info author="YourName" version="1.0" name="My First Resource" description="මගේ පළමු MTA resource එක" />
    
    <!-- Server-side scripts -->
    <script src="server.lua" type="server" />
    
    <!-- Client-side scripts -->
    <script src="client.lua" type="client" />
    
    <!-- Shared scripts -->
    <script src="shared.lua" type="shared" />
    
    <!-- Files -->
    <file src="images/logo.png" />
    <file src="sounds/notification.mp3" />
</meta>
```

**Advanced meta.xml:**
```xml
<meta>
    <info author="YourName" version="2.0" type="gamemode" />
    
    <!-- Scripts -->
    <script src="server/main.lua" type="server" />
    <script src="server/commands.lua" type="server" />
    <script src="client/gui.lua" type="client" />
    <script src="shared/config.lua" type="shared" />
    
    <!-- Files -->
    <file src="images/*.png" />
    <file src="sounds/*.mp3" />
    
    <!-- OOP භාවිතය -->
    <oop>true</oop>
    
    <!-- Exports -->
    <export function="getPlayerMoney" type="server" />
    
    <!-- Settings -->
    <settings>
        <setting name="*maxPlayers" value="32" />
        <setting name="*gamemodeText" value="Roleplay" />
    </settings>
</meta>
```

---

### 13. Server-Side Scripting

#### Server-Side Script එකක් ලියන්නේ කොහොමද:

**server.lua:**
```lua
-- Server start වෙද්දී execute වෙන code
addEventHandler("onResourceStart", resourceRoot,
    function()
        outputDebugString("Resource එක ආරම්භ විය!")
    end
)

-- Player join වෙද්දී
addEventHandler("onPlayerJoin", root,
    function()
        local playerName = getPlayerName(source)
        outputChatBox("ආයුබෝවන් " .. playerName .. "!", root, 0, 255, 0)
    end
)

-- Player quit වෙද්දී
addEventHandler("onPlayerQuit", root,
    function(quitType)
        local playerName = getPlayerName(source)
        outputChatBox(playerName .. " ක්‍රීඩාවෙන් ඉවත් විය. (" .. quitType .. ")", root, 255, 0, 0)
    end
)
```

#### Commands හදන්නේ කොහොමද:

**Simple Command:**
```lua
addCommandHandler("heal",
    function(player)
        setElementHealth(player, 100)
        outputChatBox("ඔබගේ සෞඛ්‍යය යථා තත්වයට පත් විය!", player, 0, 255, 0)
    end
)
```

**Command with Arguments:**
```lua
addCommandHandler("setmoney",
    function(player, cmd, amount)
        if not amount then
            outputChatBox("භාවිතය: /setmoney <amount>", player, 255, 0, 0)
            return
        end
        
        amount = tonumber(amount)
        if not amount then
            outputChatBox("වලංගු මුදලක් ඇතුළත් කරන්න!", player, 255, 0, 0)
            return
        end
        
        setPlayerMoney(player, amount)
        outputChatBox("ඔබගේ මුදල් " .. amount .. " දක්වා සකසා ඇත!", player, 0, 255, 0)
    end
)
```

**Admin Command:**
```lua
addCommandHandler("kick",
    function(player, cmd, targetName, ...)
        -- Admin පරීක්ෂා කිරීම
        if not isObjectInACLGroup("user." .. getAccountName(getPlayerAccount(player)), aclGetGroup("Admin")) then
            outputChatBox("ඔබට අවසරයක් නැත!", player, 255, 0, 0)
            return
        end
        
        if not targetName then
            outputChatBox("භාවිතය: /kick <player> <reason>", player, 255, 0, 0)
            return
        end
        
        local target = getPlayerFromName(targetName)
        if not target then
            outputChatBox("ක්‍රීඩකයා සොයාගත නොහැක!", player, 255, 0, 0)
            return
        end
        
        local reason = table.concat({...}, " ") or "හේතුවක් දක්වා නැත"
        
        outputChatBox(getPlayerName(target) .. " ක්‍රීඩාවෙන් දමා ඇත. හේතුව: " .. reason, root, 255, 100, 100)
        kickPlayer(target, player, reason)
    end
)
```

#### Player Data Handling:

**Element Data භාවිතය:**
```lua
-- Data set කිරීම
function givePlayerCash(player, amount)
    local currentMoney = getElementData(player, "money") or 0
    setElementData(player, "money", currentMoney + amount)
end

-- Data ලබා ගැනීම
function getPlayerCash(player)
    return getElementData(player, "money") or 0
end

-- Player spawn වෙද්දී
addEventHandler("onPlayerJoin", root,
    function()
        setElementData(source, "money", 1000)  -- Starting money
        setElementData(source, "level", 1)     -- Starting level
    end
)
```

---

### 14. Client-Side Scripting

#### Client-Side Script එකක් ලියන්නේ කොහොමද:

**client.lua:**
```lua
-- Resource start වෙද්දී
addEventHandler("onClientResourceStart", resourceRoot,
    function()
        outputChatBox("Client resource ආරම්භ විය!", 0, 255, 0)
    end
)

-- Key press detect කිරීම
bindKey("F1", "down",
    function()
        outputChatBox("ඔබ F1 ඔබනු ලැබීය!", 0, 255, 255)
    end
)

-- Mouse click detect කිරීම
addEventHandler("onClientClick", root,
    function(button, state, absoluteX, absoluteY, worldX, worldY, worldZ, clickedElement)
        if button == "left" and state == "down" then
            if clickedElement and getElementType(clickedElement) == "vehicle" then
                local vehicleName = getVehicleName(clickedElement)
                outputChatBox("ඔබ " .. vehicleName .. " එකක් click කළා!", 0, 255, 0)
            end
        end
    end
)
```

#### Render Functions (Screen මත draw කිරීම):

**dxDraw භාවිතය:**
```lua
-- Text draw කිරීම
addEventHandler("onClientRender", root,
    function()
        local screenWidth, screenHeight = guiGetScreenSize()
        
        -- Screen මැද text එකක්
        dxDrawText("ආයුබෝවන් MTA:SA!", 
            0, 0, screenWidth, screenHeight,
            tocolor(255, 255, 255, 255),
            2, "default", "center", "center")
    end
)

-- Rectangle draw කිරීම
function drawHealthBar()
    local health = getElementHealth(localPlayer)
    local maxHealth = 100
    local barWidth = 200
    local barHeight = 20
    local x = 20
    local y = 20
    
    -- Background
    dxDrawRectangle(x, y, barWidth, barHeight, tocolor(0, 0, 0, 150))
    
    -- Health bar
    local healthWidth = (health / maxHealth) * barWidth
    dxDrawRectangle(x, y, healthWidth, barHeight, tocolor(255, 0, 0, 200))
    
    -- Text
    dxDrawText("HP: " .. math.floor(health), x, y, x + barWidth, y + barHeight, 
        tocolor(255, 255, 255, 255), 1, "default", "center", "center")
end

addEventHandler("onClientRender", root, drawHealthBar)

-- Image draw කිරීම
addEventHandler("onClientResourceStart", resourceRoot,
    function()
        -- Image load කිරීම
        local logoTexture = dxCreateTexture("images/logo.png")
        
        addEventHandler("onClientRender", root,
            function()
                if logoTexture then
                    dxDrawImage(10, 10, 128, 128, logoTexture)
                end
            end
        )
    end
)
```
### 15. Events සහ Event Handlers

#### Events කියන්නේ මොකද්ද?
Events යනු MTA වල සිදු වන විවිධ ක්‍රියා (player join, vehicle enter, chat message, etc). අපි event handlers භාවිතයෙන් මේවාට ප්‍රතිචාර දක්වනවා.

#### Server-Side Events:

**මූලික Event Handling:**
```lua
-- Player join event
addEventHandler("onPlayerJoin", root,
    function()
        local playerName = getPlayerName(source)
        outputChatBox("🌟 " .. playerName .. " සර්වරයට සම්බන්ධ විය!", root, 255, 255, 0)
        
        -- Player ගේ නම set කිරීම
        setPlayerName(source, playerName)
    end
)

-- Player quit event
addEventHandler("onPlayerQuit", root,
    function(reason)
        local playerName = getPlayerName(source)
        outputChatBox("👋 " .. playerName .. " සර්වරයෙන් ඉවත් විය (" .. reason .. ")", root, 255, 100, 100)
    end
)

-- Player chat event
addEventHandler("onPlayerChat", root,
    function(message, messageType)
        if messageType == 0 then  -- Normal chat
            local playerName = getPlayerName(source)
            outputChatBox("💬 " .. playerName .. ": " .. message, root, 255, 255, 255)
            cancelEvent()  -- Default chat message cancel කිරීම
        end
    end
)
```

**Vehicle Events:**
```lua
-- Player vehicle enter
addEventHandler("onPlayerVehicleEnter", root,
    function(vehicle, seat, jacked)
        local playerName = getPlayerName(source)
        local vehicleName = getVehicleName(vehicle)
        
        if seat == 0 then  -- Driver seat
            outputChatBox("🚗 " .. playerName .. " " .. vehicleName .. " රථය drive කරයි", root, 0, 255, 0)
        else
            outputChatBox("🚗 " .. playerName .. " " .. vehicleName .. " රථයේ ගමන් කරයි", root, 0, 200, 0)
        end
    end
)

-- Vehicle damage
addEventHandler("onVehicleDamage", root,
    function(loss)
        local health = getElementHealth(source)
        if health < 300 then
            outputChatBox("⚠️ රථය හානි වී ඇත! සෞඛ්‍යය: " .. math.floor(health), root, 255, 100, 0)
        end
    end
)
```

#### Client-Side Events:

**Render Events:**
```lua
-- Screen මත FPS display කිරීම
local fps = 0
local frames = 0
local lastTick = getTickCount()

addEventHandler("onClientRender", root,
    function()
        frames = frames + 1
        
        local currentTick = getTickCount()
        if currentTick - lastTick >= 1000 then
            fps = frames
            frames = 0
            lastTick = currentTick
        end
        
        dxDrawText("FPS: " .. fps, 10, 50, nil, nil, tocolor(255, 255, 255, 255), 1, "default")
    end
)
```

**Key Events:**
```lua
-- Key bindings
bindKey("F2", "down",
    function()
        outputChatBox("🎮 ඔබ F2 යතුර ඔබනු ලැබීය!", 255, 255, 0)
        
        -- Vehicle spawn කිරීම
        local player = localPlayer
        local x, y, z = getElementPosition(player)
        local vehicle = createVehicle(411, x + 3, y, z)  -- Infernus
        
        if vehicle then
            warpPedIntoVehicle(player, vehicle)
            outputChatBox("🚗 Infernus රථය spawn කරන ලදී!", 0, 255, 0)
        end
    end
)

-- Multiple keys
bindKey("lshift", "down",
    function()
        setControlState("sprint", true)
    end
)

bindKey("lshift", "up",
    function()
        setControlState("sprint", false)
    end
)
```

#### Custom Events හදන්නේ කොහොමද:

**Server-Side Custom Event:**
```lua
-- Custom event define කිරීම
function givePlayerReward(player, rewardType, amount)
    if not isElement(player) then return false end
    
    local rewardData = {
        player = player,
        type = rewardType,
        amount = amount,
        timestamp = getRealTime().timestamp
    }
    
    -- Custom event trigger කිරීම
    triggerEvent("onPlayerReward", player, rewardData)
    
    return true
end

-- Custom event handle කිරීම
addEvent("onPlayerReward", true)
addEventHandler("onPlayerReward", root,
    function(rewardData)
        local playerName = getPlayerName(source)
        outputChatBox("🎁 " .. playerName .. " සම්මානයක් ලැබුණි: " .. rewardData.type, root, 0, 255, 0)
        
        -- Reward එක process කිරීම
        if rewardData.type == "money" then
            givePlayerMoney(source, rewardData.amount)
            outputChatBox("💰 ඔබට ඩොලර් " .. rewardData.amount .. " ලැබුණි!", source, 0, 255, 0)
        elseif rewardData.type == "experience" then
            local currentXP = getElementData(source, "experience") or 0
            setElementData(source, "experience", currentXP + rewardData.amount)
            outputChatBox("⭐ ඔබට XP " .. rewardData.amount .. " ලැබුණි!", source, 255, 255, 0)
        end
    end
)
```

**Client to Server Communication:**
```lua
-- Client-side: Event trigger කිරීම
function requestVehicleSpawn(vehicleModel)
    if not vehicleModel then return false end
    
    triggerServerEvent("onClientRequestVehicle", localPlayer, vehicleModel)
    return true
end

-- Server-side: Event handle කිරීම
addEvent("onClientRequestVehicle", true)
addEventHandler("onClientRequestVehicle", root,
    function(vehicleModel)
        if not isElement(source) then return end
        
        local x, y, z = getElementPosition(source)
        local vehicle = createVehicle(vehicleModel, x + 5, y, z)
        
        if vehicle then
            warpPedIntoVehicle(source, vehicle)
            outputChatBox("🚗 රථය spawn කරන ලදී!", source, 0, 255, 0)
        else
            outputChatBox("❌ රථය spawn කිරීමට නොහැක!", source, 255, 0, 0)
        end
    end
)
```

---

### 16. Elements සහ Data

#### Elements කියන්නේ මොකද්ද?
MTA වල හැම දෙයක්ම element එකක්: players, vehicles, objects, markers, etc.

#### Element Types:
```lua
-- Element types
local elementTypes = {
    "player", "vehicle", "object", "marker", "blip", "pickup", "radararea", "team"
}

-- Element type check කිරීම
function isValidPlayer(element)
    return isElement(element) and getElementType(element) == "player"
end

function isValidVehicle(element)
    return isElement(element) and getElementType(element) == "vehicle"
end
```

#### Element Data Management:

**Element Data භාවිතය:**
```lua
-- Player data management
function setupPlayerData(player)
    if not isElement(player) then return false end
    
    -- Basic player data
    setElementData(player, "money", 1000)
    setElementData(player, "level", 1)
    setElementData(player, "experience", 0)
    setElementData(player, "playTime", 0)
    setElementData(player, "kills", 0)
    setElementData(player, "deaths", 0)
    
    return true
end

-- Data ලබා ගැනීම
function getPlayerStats(player)
    if not isValidPlayer(player) then return nil end
    
    return {
        money = getElementData(player, "money") or 0,
        level = getElementData(player, "level") or 1,
        experience = getElementData(player, "experience") or 0,
        playTime = getElementData(player, "playTime") or 0,
        kills = getElementData(player, "kills") or 0,
        deaths = getElementData(player, "deaths") or 0
    }
end

-- Data update කිරීම
function addPlayerMoney(player, amount)
    if not isValidPlayer(player) or not amount then return false end
    
    local currentMoney = getElementData(player, "money") or 0
    setElementData(player, "money", currentMoney + amount)
    
    -- Custom event trigger කිරීම
    triggerEvent("onPlayerMoneyChange", player, amount, currentMoney + amount)
    
    return true
end
```

#### Element Creation සහ Destruction:

**Vehicles Create කිරීම:**
```lua
-- Vehicle spawn function
function spawnPlayerVehicle(player, model, x, y, z)
    if not isValidPlayer(player) then return nil end
    
    -- Position නොමැතිනම් player position එක භාවිතා කිරීම
    if not x or not y or not z then
        x, y, z = getElementPosition(player)
        x = x + 3  -- Player ගෙන් 3 units දුරින්
    end
    
    local vehicle = createVehicle(model or 411, x, y, z)  -- Default: Infernus
    
    if vehicle then
        -- Vehicle data set කිරීම
        setElementData(vehicle, "owner", player)
        setElementData(vehicle, "spawnTime", getRealTime().timestamp)
        
        -- Player ගේ vehicle list එකට add කිරීම
        local playerVehicles = getElementData(player, "vehicles") or {}
        table.insert(playerVehicles, vehicle)
        setElementData(player, "vehicles", playerVehicles)
        
        warpPedIntoVehicle(player, vehicle)
        outputChatBox("🚗 රථය spawn කරන ලදී!", player, 0, 255, 0)
    else
        outputChatBox("❌ රථය spawn කිරීමට නොහැක!", player, 255, 0, 0)
    end
    
    return vehicle
end
```

**Markers සහ Blips:**

```lua
-- Marker create කිරීම
function createSafeZone(x, y, z, size)
    local marker = createMarker(x, y, z, "cylinder", size, 0, 255, 0, 150)
    
    if marker then
        -- Marker events
        addEventHandler("onMarkerHit", marker, onSafeZoneEnter)
        addEventHandler("onMarkerLeave", marker, onSafeZoneExit)
        
        -- Blip create කිරීම
        local blip = createBlip(x, y, z, 0, 2, 0, 255, 0, 255, 0, 99999)
        setElementData(blip, "safeZone", true)
        
        return marker, blip
    end
    
    return nil
end

-- Marker hit event
function onSafeZoneEnter(hitElement, matchingDimension)
    if getElementType(hitElement) == "player" and matchingDimension then
        outputChatBox("🛡️ ඔබ සුරක්ෂිත කලාපයකට පිවිසියි!", hitElement, 0, 255, 0)
        setElementData(hitElement, "inSafeZone", true)
    end
end

function onSafeZoneExit(hitElement, matchingDimension)
    if getElementType(hitElement) == "player" and matchingDimension then
        outputChatBox("⚠️ ඔබ සුරක්ෂිත කලාපයෙන් පිටව ගියි!", hitElement, 255, 100, 0)
        setElementData(hitElement, "inSafeZone", false)
    end
end
```

---

### 17. GUI Development

#### GUI Elements:

**මූලික GUI Creation:**
```lua
-- GUI variables
local screenWidth, screenHeight = guiGetScreenSize()
local guiElements = {}

-- Main window create කිරීම
function createMainMenu()
    -- Window
    guiElements.window = guiCreateWindow(screenWidth/2-150, screenHeight/2-200, 300, 400, "මුල් මෙනුව", false)
    guiWindowSetSizable(guiElements.window, false)
    
    -- Buttons
    guiElements.playButton = guiCreateButton(50, 50, 200, 40, "ක්‍රීඩාව අරඹන්න", false, guiElements.window)
    guiElements.settingsButton = guiCreateButton(50, 110, 200, 40, "සැකසුම්", false, guiElements.window)
    guiElements.quitButton = guiCreateButton(50, 170, 200, 40, "පිටවීම", false, guiElements.window)
    
    -- Labels
    guiElements.titleLabel = guiCreateLabel(0, 10, 300, 30, "MTA:SA Roleplay", false, guiElements.window)
    guiLabelSetHorizontalAlign(guiElements.titleLabel, "center")
    
    -- Events
    addEventHandler("onClientGUIClick", guiElements.playButton, onPlayClick, false)
    addEventHandler("onClientGUIClick", guiElements.settingsButton, onSettingsClick, false)
    addEventHandler("onClientGUIClick", guiElements.quitButton, onQuitClick, false)
    
    -- Initially hide කිරීම
    guiSetVisible(guiElements.window, false)
end

-- Button click events
function onPlayClick()
    guiSetVisible(guiElements.window, false)
    showCursor(false)
    triggerServerEvent("onClientRequestSpawn", localPlayer)
end

function onSettingsClick()
    createSettingsMenu()
end

function onQuitClick()
    triggerServerEvent("onClientRequestQuit", localPlayer)
end

-- Menu toggle කිරීම
function toggleMainMenu()
    local visible = not guiGetVisible(guiElements.window)
    guiSetVisible(guiElements.window, visible)
    showCursor(visible)
end

-- F1 key bind
bindKey("F1", "down", toggleMainMenu)
```

**DX GUI (More Advanced):**
```lua
-- DX based GUI
local dxGUI = {
    visible = false,
    elements = {}
}

function createDXButton(x, y, width, height, text, onClick)
    local button = {
        x = x, y = y, width = width, height = height,
        text = text, onClick = onClick,
        hover = false, click = false
    }
    
    table.insert(dxGUI.elements, button)
    return button
end

function drawDXGUI()
    if not dxGUI.visible then return end
    
    -- Background
    dxDrawRectangle(0, 0, screenWidth, screenHeight, tocolor(0, 0, 0, 150))
    
    -- Main panel
    local panelWidth, panelHeight = 400, 300
    local panelX, panelY = (screenWidth - panelWidth)/2, (screenHeight - panelHeight)/2
    
    dxDrawRectangle(panelX, panelY, panelWidth, panelHeight, tocolor(50, 50, 50, 200))
    dxDrawRectangle(panelX, panelY, panelWidth, 30, tocolor(0, 100, 200, 255))
    dxDrawText("DX GUI Panel", panelX, panelY, panelX + panelWidth, panelY + 30, 
        tocolor(255, 255, 255, 255), 1, "default", "center", "center")
    
    -- Elements draw කිරීම
    for _, element in ipairs(dxGUI.elements) do
        local color = tocolor(100, 100, 100, 200)
        
        if element.hover then
            color = tocolor(120, 120, 120, 200)
        end
        
        if element.click then
            color = tocolor(80, 80, 80, 200)
        end
        
        dxDrawRectangle(element.x, element.y, element.width, element.height, color)
        dxDrawText(element.text, element.x, element.y, element.x + element.width, element.y + element.height,
            tocolor(255, 255, 255, 255), 1, "default", "center", "center")
    end
end

function handleDXGUIClick(button, state, absoluteX, absoluteY)
    if not dxGUI.visible or button ~= "left" or state ~= "down" then return end
    
    for _, element in ipairs(dxGUI.elements) do
        if absoluteX >= element.x and absoluteX <= element.x + element.width and
           absoluteY >= element.y and absoluteY <= element.y + element.height then
           
            element.click = true
            if element.onClick then
                element.onClick()
            end
        end
    end
end

-- Event handlers
addEventHandler("onClientRender", root, drawDXGUI)
addEventHandler("onClientClick", root, handleDXGUIClick)
```

---

### 18. Database Integration

#### SQLite Database:

**Database Connection:**
```lua
-- Database connection
local db = nil

function connectDatabase()
    if db then return db end
    
    db = dbConnect("sqlite", ":/players.db")
    
    if not db then
        outputDebugString("Database connection failed!")
        return nil
    end
    
    outputDebugString("Database connected successfully!")
    createTables()
    return db
end

-- Tables create කිරීම
function createTables()
    if not db then return false end
    
    -- Players table
    dbExec(db, [[
        CREATE TABLE IF NOT EXISTS players (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            account TEXT UNIQUE,
            name TEXT,
            money INTEGER DEFAULT 1000,
            level INTEGER DEFAULT 1,
            experience INTEGER DEFAULT 0,
            play_time INTEGER DEFAULT 0,
            created_at DATETIME DEFAULT CURRENT_TIMESTAMP
        )
    ]])
    
    -- Vehicles table
    dbExec(db, [[
        CREATE TABLE IF NOT EXISTS vehicles (
            id INTEGER PRIMARY KEY AUTOINCREMENT,
            owner_account TEXT,
            model INTEGER,
            pos_x REAL,
            pos_y REAL,
            pos_z REAL,
            rotation REAL,
            color1 INTEGER,
            color2 INTEGER,
            created_at DATETIME DEFAULT CURRENT_TIMESTAMP
        )
    ]])
    
    outputDebugString("Database tables created!")
    return true
end
```

**Player Data Save/Load:**
```lua
-- Player data save කිරීම
function savePlayerData(player)
    if not isValidPlayer(player) or not db then return false end
    
    local account = getPlayerAccount(player)
    if not account or isGuestAccount(account) then return false end
    
    local accountName = getAccountName(account)
    local playerName = getPlayerName(player)
    local money = getElementData(player, "money") or 0
    local level = getElementData(player, "level") or 1
    local experience = getElementData(player, "experience") or 0
    local playTime = getElementData(player, "playTime") or 0
    
    -- Check if player exists
    local query = dbQuery(db, "SELECT id FROM players WHERE account = ?", accountName)
    local result = dbPoll(query, -1)
    
    if result and #result > 0 then
        -- Update existing player
        dbExec(db, 
            "UPDATE players SET name = ?, money = ?, level = ?, experience = ?, play_time = ? WHERE account = ?",
            playerName, money, level, experience, playTime, accountName
        )
    else
        -- Insert new player
        dbExec(db,
            "INSERT INTO players (account, name, money, level, experience, play_time) VALUES (?, ?, ?, ?, ?, ?)",
            accountName, playerName, money, level, experience, playTime
        )
    end
    
    outputDebugString("Player data saved: " .. playerName)
    return true
end

-- Player data load කිරීම
function loadPlayerData(player)
    if not isValidPlayer(player) or not db then return false end
    
    local account = getPlayerAccount(player)
    if not account or isGuestAccount(account) then return false end
    
    local accountName = getAccountName(account)
    local query = dbQuery(db, "SELECT * FROM players WHERE account = ?", accountName)
    local result = dbPoll(query, -1)
    
    if result and #result > 0 then
        local data = result[1]
        
        -- Element data set කිරීම
        setElementData(player, "money", data.money)
        setElementData(player, "level", data.level)
        setElementData(player, "experience", data.experience)
        setElementData(player, "playTime", data.play_time)
        
        outputChatBox("📊 ඔබගේ දත්ත ලබා ගන්නා ලදී!", player, 0, 255, 0)
        return true
    else
        -- New player setup
        setupPlayerData(player)
        outputChatBox("👋 සාදරයෙන් පිළිගනිමු! ඔබගේ නව ගිණුම සාදන ලදී.", player, 0, 255, 0)
        return true
    end
end
```

**Auto-save System:**
```lua
-- Auto-save timer
setTimer(
    function()
        for _, player in ipairs(getElementsByType("player")) do
            savePlayerData(player)
        end
        outputDebugString("Auto-save completed!")
    end,
    300000, 0  -- 5 minutes
)

-- Player quit වෙද්දී save කිරීම
addEventHandler("onPlayerQuit", root,
    function()
        savePlayerData(source)
    end
)
```

---

### 19. Advanced Concepts

#### OOP (Object-Oriented Programming):

**Player Class:**
```lua
-- Player class definition
Player = {}
Player.__index = Player

function Player:create(account)
    local instance = {}
    setmetatable(instance, Player)
    
    instance.account = account
    instance.element = nil
    instance.data = {}
    
    return instance
end

function Player:setElement(playerElement)
    if not isValidPlayer(playerElement) then return false end
    self.element = playerElement
    return true
end

function Player:getMoney()
    return getElementData(self.element, "money") or 0
end

function Player:addMoney(amount)
    if not amount then return false end
    
    local current = self:getMoney()
    setElementData(self.element, "money", current + amount)
    
    triggerEvent("onPlayerMoneyChange", self.element, amount, current + amount)
    return true
end

function Player:save()
    return savePlayerData(self.element)
end

-- Player manager
PlayerManager = {
    players = {}
}

function PlayerManager:getPlayer(account)
    return self.players[account]
end

function PlayerManager:addPlayer(account, playerElement)
    local player = Player:create(account)
    player:setElement(playerElement)
    
    self.players[account] = player
    return player
end

function PlayerManager:removePlayer(account)
    local player = self.players[account]
    if player then
        player:save()
        self.players[account] = nil
    end
end
```

#### Performance Optimization:

**Efficient Event Handling:**
```lua
-- Event handler optimization
local eventHandlers = {}

function addOptimizedEventHandler(eventName, attachedTo, handler)
    if not eventHandlers[eventName] then
        eventHandlers[eventName] = {}
    end
    
    table.insert(eventHandlers[eventName], {
        attachedTo = attachedTo,
        handler = handler
    })
    
    addEventHandler(eventName, attachedTo, handler)
end

function removeOptimizedEventHandlers(eventName)
    if eventHandlers[eventName] then
        for _, handlerData in ipairs(eventHandlers[eventName]) do
            removeEventHandler(eventName, handlerData.attachedTo, handlerData.handler)
        end
        eventHandlers[eventName] = nil
    end
end
```

**Memory Management:**
```lua
-- Garbage collection
function cleanupUnusedElements()
    local count = 0
    
    -- Clean up unused vehicles
    for _, vehicle in ipairs(getElementsByType("vehicle")) do
        if not getElementData(vehicle, "inUse") then
            if getElementHealth(vehicle) < 250 then
                destroyElement(vehicle)
                count = count + 1
            end
        end
    end
    
    outputDebugString("Cleanup completed: " .. count .. " elements removed")
end

-- Regular cleanup
setTimer(cleanupUnusedElements, 60000, 0)  -- 1 minute
```

---

### 20. Best Practices

#### Code Organization:

**Modular Structure:**
```
resources/
└── mygamemode/
    ├── meta.xml
    ├── main.lua
    ├── config.lua
    ├── modules/
    │   ├── player/
    │   │   ├── manager.lua
    │   │   ├── inventory.lua
    │   │   └── skills.lua
    │   ├── vehicles/
    │   │   ├── manager.lua
    │   │   ├── spawner.lua
    │   │   └── tuning.lua
    │   └── database/
    │       ├── connection.lua
    │       ├── players.lua
    │       └── vehicles.lua
    ├── client/
    │   ├── gui/
    │   │   ├── main.lua
    │   │   ├── hud.lua
    │   │   └── inventory.lua
    │   └── rendering/
    │       ├── main.lua
    │       └── effects.lua
    └── shared/
        ├── utils.lua
        └── constants.lua
```

#### Security Best Practices:

**Input Validation:**
```lua
function validatePlayerInput(player, input, maxLength)
    if not isValidPlayer(player) then return false end
    if not input or type(input) ~= "string" then return false end
    if #input > (maxLength or 128) then return false end
    
    -- Remove harmful characters
    local cleanInput = string.gsub(input, "[<>\"']", "")
    
    return cleanInput
end

-- Admin command validation
function isPlayerAdmin(player)
    if not isValidPlayer(player) then return false end
    
    local account = getPlayerAccount(player)
    if not account or isGuestAccount(account) then return false end
    
    local accountName = getAccountName(account)
    return isObjectInACLGroup("user." .. accountName, aclGetGroup("Admin"))
end
```

#### Error Handling:

**Comprehensive Error Handling:**
```lua
function safeFunctionCall(func, ...)
    local results = {pcall(func, ...)}
    
    if not results[1] then
        local errorMsg = results[2] or "Unknown error"
        outputDebugString("Function error: " .. errorMsg, 1)
        return false, errorMsg
    end
    
    return unpack(results, 2)
end

-- Usage
local success, result = safeFunctionCall(riskyOperation, param1, param2)
if success then
    -- Process result
else
    -- Handle error
    outputChatBox("Operation failed: " .. result, player, 255, 0, 0)
end
```

#### Documentation:

**Code Documentation:**
```lua
--- Player money management system
-- @module player_money
-- @author Omindu Dissanayaka
-- @license MIT

--- Adds money to player's account
-- @function addPlayerMoney
-- @param player userdata The player element
-- @param amount number The amount to add
-- @return boolean True if successful, false otherwise
-- @usage addPlayerMoney(player, 1000)
function addPlayerMoney(player, amount)
    -- Function implementation
end
```

---

## 🎉 සාරාංශය

මෙම මාර්ගෝපදේශය ඔබට Lua programming සහ MTA:SA resource development හි සම්පූර්ණ පදනම ලබා දෙනු ඇත. මතක තබා ගන්න:

### 🔑 ප්‍රධාන කරුණු:
1. **Lua basics** හොඳින් ඉගෙන ගන්න
2. **MTA events** සහ **element system** භාවිතය හැසිරවීම ඉගෙන ගන්න
3. **Server-client communication** හරිහැටි තේරුම් ගන්න
4. **Database integration** සහ **data management** හොඳින් කරන්න
5. **Code organization** සහ **best practices** අනුගමනය කරන්න

### 🚀 ඊළඟ පියවර:
1. සරල resources සිට පටන් ගන්න
2. ක්‍රමයෙන් complex features add කරන්න
3. MTA wiki සහ community forums භාවිතා කරන්න
4. දෝෂ නිරාකරණය කිරීම ඉගෙන ගන්න
5. අන් අයගේ code අධ්‍යයනය කරන්න

### 📚 අමතර resources:
- [MTA Wiki](https://wiki.multitheftauto.com/)
- [Lua Documentation](https://www.lua.org/manual/5.1/)
- [MTA Forums](https://forum.mtasa.com/)

**සාදරයෙන් පිළිගනිමු MTA:SA development community එකට!** 🎮

මෙම මාර්ගෝපදේශය ඔබගේ development ගමන ආරම්භ කිරීමට උපකාරී වනු ඇතැයි අපි විශ්වාස කරමු. කේතනය කිරීමේ අභියෝගාත්මක සහ රසවත් ලෝකය භුක්ති විඳින්න! ✨
