
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
Config.BlackMoneyItem = 'black_money'
Config.CleanBundleItem = 'clean_bundle'
Config.CashItem = 'cash'
Config.DamagedNoteItem = 'damaged_note'

Config.DamagedNotes = {
    min = 5,
    max = 20
}

Config.Leveling = {
    Enabled = true,
    XpPerCleanBundle = 10,
    Levels = {
        [1] = { xp = 0, multiplier = 1 },
        [2] = { xp = 100, multiplier = 2 },
        [3] = { xp = 250, multiplier = 3 },
        [4] = { xp = 500, multiplier = 4 },
        [5] = { xp = 1000, multiplier = 5 }
    }
}
```

Customize:
- PED model and location
- Marker positions
- Damage ratios
- XP gain and progression curve

### 4. 📜 Add to your `server.cfg`

```cfg
ensure ox_lib
ensure ox_inventory
ensure ox_target
ensure moneywash
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

## 🧾 Customization Options

- Enable job/gang-only access
- Adjust XP progression speed and difficulty
- Add Discord logging or webhook alerts
- Modify animations and UI visuals
- Add police alert logic or laundering cooldown

🛒 **[Get the latest version and updates here](https://rf-scripts.tebex.io/)**

---

## 👨‍💻 Developer Info

- 💡 Optimized for `ox` ecosystem
- 🧪 100% exploitable-safe (no client-side logic exploits)
- ✨ Clean, maintainable code with animations and effects
- 📁 Full source code available after purchase

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
