
# 💸 Advanced Money Wash System for QBCore & QBox

An immersive and interactive money laundering system built for QBCore using `ox_inventory`, `ox_lib`, and `ox_target`. This system simulates real-life laundering steps and includes a full progression system with leveling and multipliers.

🛒 **[Click here to purchase this script](https://rf-scripts.tebex.io/)** 

---

## 🚀 Features

- 🧼 **Step-by-step laundering process**
  - ✅ Count dirty money (with animation and NUI feedback)
  - ✅ Clean money (convert black_money to clean_bundle)
  - ✅ Sort bundles (turn clean_bundle into usable cash + damaged notes)

- 🧠 **Fully automated, immersive progression**
  - Just press once per stage — the script handles everything in real-time
  - Player is frozen & animated during work
  - Smooth NUI animations
  - NUI stays open for 5s after last step

- 📈 **Leveling & XP System**
  - +10 XP per clean bundle (Can be changed)
  - Auto-leveling with configurable XP thresholds
  - Each level increases how much you can process per second
  - All XP is saved to the SQL database

- 🎬 **Immersive details**
  - 3D marker only above current active step
  - PED target interaction to launch session
  - Live, smooth UI counters for counted, bundles, cash, damaged
  - Safe from exploits

🛒 **[Buy now to get access](https://rf-scripts.tebex.io/)**

---

## 📦 Dependencies

- [ox_inventory](https://overextended.dev/ox_inventory/)
- [ox_lib](https://overextended.dev/ox_lib/)
- [ox_target](https://overextended.dev/ox_target/)
- QBCore Framework
or
- QBox Framework




---

## 🛠️ Installation Guide

### 1. ⬇️ Install the Resource

Place the `moneywash` folder inside your `resources` directory.

### 2. 🧬 Setup the SQL Table

Run this SQL query in your database:

```sql
CREATE TABLE IF NOT EXISTS `moneywash_xp` (
  `citizenid` VARCHAR(50) NOT NULL,
  `xp` INT NOT NULL DEFAULT 0,
  PRIMARY KEY (`citizenid`)
);
```

### 3. ⚙️ Configure the Script

Edit `config.lua`:

```lua
--[[
    _/_/_/    _/_/_/_/        _/_/_/    _/_/_/  _/_/_/    _/_/_/  _/_/_/    _/_/_/_/_/    _/_/_/   
   _/    _/  _/            _/        _/        _/    _/    _/    _/    _/      _/      _/          
  _/_/_/    _/_/_/          _/_/    _/        _/_/_/      _/    _/_/_/        _/        _/_/       
 _/    _/  _/                  _/  _/        _/    _/    _/    _/            _/            _/      
_/    _/  _/            _/_/_/      _/_/_/  _/    _/  _/_/_/  _/            _/      _/_/_/  
]]

Config = {}

Config.BlackMoneyItem = 'black_money' -- Item name for your marked bills/dirty money in your server
Config.CleanBundleItem = 'clean_bundle' -- Item name for the Clean Bundle Cash - Can use the default provided for ox_inventory or qb-inventory
Config.CashItem = 'cash' -- Item name for cash in your server
Config.DamagedNoteItem = 'damaged_note' -- Item name for damaged notes in your server - Can you the feault provided for ox_inventory or qb-inventory

-- The minimum and maximum amount of damaged notes per Clean Cash Bundle
Config.DamagedNotes = {
    min = 100,
    max = 120
}

----------------------------
-- Leveling system config --
----------------------------
Config.Leveling = {
    Enabled = true, -- true = Leveling system enabled | false = Leveling system disabled
    XpPerCleanBundle = 1, -- How much xp a player gains per clean bundle that they get
    Levels = {                                  -- You can add more levels here if you want
        [1] = { xp = 0,    multiplier = 1 },    -- xp = Amount of xp to unlock that specified multiplier
        [2] = { xp = 1000,  multiplier = 2 },   -- multiplier = How many times the items will be multiplied (e.g. multiplier = 2 | That means that you will recieve 2 x the original amount)
        [3] = { xp = 2000,  multiplier = 4 },
        [4] = { xp = 4000,  multiplier = 8 },
        [5] = { xp = 8000, multiplier = 16 },
    --  [6] = { xp = 16000, multiplier = 32 },
    }
}

---------------------------
-- Money wash ped config --
---------------------------
Config.MoneyWashPed = {
    model = 'cs_bankman', -- The model for the money wash ped (You can find all of the peds available here: https://wiki.rage.mp/wiki/Peds)
    coords = vec4(1138.05, -3196.38, -39.67, 139.68), -- The location of the money wash ped (Make sure that you use the vector 4)
    label = 'Money Wash' -- The label that you will see when you third-eye the money wash ped
}

-------------------------------------
-- Money wash process steps config --
-------------------------------------
Config.StepLocations = {
    [1] = {
        label = "Count Dirty Money", -- The label that you will see when third-eye each step
        coords = vector3(1120.0081, -3198.1414, -40.6393), -- Location of each step (Make sure that you use vector3)
        heading = 180.0 -- IGNORE THIS
    },
    [2] = {
        label = "Clean the Money",
        coords = vector3(1133.4917, -3198.3662, -39.9209),
        heading = 180.0
    },
    [3] = {
        label = "Sort Clean Bundles",
        coords = vector3(1116.3629, -3194.9351, -40.6057),
        heading = 180.0
    }
    ----------------- NOTE ------------------
    -- YOU ARE NOT ABLE TO ADD EXTRA STEPS --
    -----------------------------------------
}
```

Customize:
- PED model and location
- Marker positions
- Damage ratios
- XP gain and progression curve

### 4. 📜 Add to your `server.cfg` in this order!!!

```cfg
ensure ox_lib
ensure ox_inventory
ensure ox_target
ensure rf_moneywash
```

---

## 🔄 How It Works

1. 🧑 Talk to the Money Wash PED (via ox_target)
2. ✅ Start session — NUI opens with stats
3. 🪙 Count dirty money → convert to wet_bundle
4. 🧼 Clean dirty ink → convert to clean_bundle
5. 💵 Sort bundles → receive cash & damaged_note
6. 🆙 Earn XP and level up automatically
7. 🔁 Repeat for faster processing per level

---



🛒 **[Get the latest version and updates here](https://rf-scripts.tebex.io/)**

---

## 👨‍💻 Developer Info

- 💡 Optimized for `ox` ecosystem
- 🧪 100% exploitable-safe (no client-side logic exploits)

---

## 🤝 Support

Need help or want to request a feature?

- 📩 Contact us via Discord: **Not available just yet**
- 📌 Stay up to date by following our **Coming soon!**

---

## 📜 License

This script is not open source and is protected by license and cfx escrow system.  
You may not redistribute or resell this script without permission.

🛒 **[Purchase license here](https://rf-scripts.tebex.io/)**
