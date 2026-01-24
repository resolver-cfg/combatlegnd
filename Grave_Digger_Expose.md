# Exposing: The larp taro and Pasted Anti cheat , Grave Digger & Decaying winter
#### 4 Months of Research | January 2026
> "This isn't just broken code. This is deliberate negligence."

> [!WARNING]
> **DISCLAIMER:** The information in this document was gathered by **Nigginality Hub** over 4 months of research (September 2025 - January 2026). Every claim is backed by verifiable evidence including decompiled game code, public DevForum posts, and direct conversations with game management.

## Who Gathered This Information
| Name | User ID | Role |
| :--- | :--- | :--- |
| **Resolver** (Resolver) | 923300723662393454 | Owner, Lead Researcher |
| **Reign** (__reignful) | 1055910977759096992 | Exploit Development |

*Exclusively Released at **Nigginality Hub** - The Best Exploits for Decaying Winter & Grave Digger*

---

## What We're Exposing
We are exposing **Grave Digger** and **Decaying Winter** for:
1.  **PASTED ANTI-CHEAT**: **Taro** copied their entire "Labyrinth" anti-cheat from a public DevForum post that community developers called "garbage" within 48 hours. **Archeximus** has nothing to do with it; the developer **Taro** is the one responsible.
2.  **BROKEN ALT DETECTION**: Their alt detection only works in tutorial mode. Players can bypass it by getting kicked or extending the game in tutorial; rejoining will teleport you to the main game.
3.  **NO INTENTION TO FIX**: When confronted, management bans the reporter and ignores the security hole.

### The Games Involved
| Game | Developer | Visits | Status |
| :--- | :--- | :--- | :--- |
| **Grave Digger** | Archeximus | 33M+ | Uses "Labyrinth" |
| **Decaying Winter** | Archeximus / Zym | 60M+ | Uses "Labyrinth" |

---

## Management Admits Everything
> [!CAUTION]
> **The Conversation**: On January 9, 2025, we confronted the Game Manager (`hharley`, User ID: `572027926833528833`) with proof of their broken system.

**The Exploit**: Alt detection *only works in tutorial mode*. If you get kicked or leave in the tutorial and rejoin, it **teleports you to the main game**, bypassing the check completely.

**Manager's Response?** "banned lmao"

```text
[3:33:48 AM] Resolver: your game anti alt or whatever its called is shit
[3:33:51 AM] Resolver: its gotta be fixed
[3:34:16 AM] Resolver: anti alt only works on the tutorial mode
[3:34:21 AM] Resolver: you get kicked
[3:34:25 AM] Resolver: and then rejoin again
[3:34:39 AM] Resolver: it will teleport you to the main game
...
[3:34:49 AM] hharley: banned lmao
```
*[Full Transcript (https://dashboard.tickets.bot/manage/1255891838833786960/transcripts/view/5035) Available at End of Document]*

**Verdict**: Management knows their system is broken and chooses to ban reporters rather than fix it.

---

## The Pasted Anti-Cheat: "Labyrinth"
**Taro** stole the exact code from a public DevForum post, obfuscated it, and called it "Labyrinth". We decompiled "Labyrinth" and compared it to the public code.

### Code Comparison
#### 1. The Original (DevForum)
The original code returned `workspace` calls directly.
```lua
local metamethods = {
    __namecall = function() return workspace:__z() end,
    __index = function() return workspace.__z end,
    __newindex = function() workspace.__z = true end,
    __add = function() return p1 + p2 end,
    __sub = function() return p1 - p2 end,
    -- ... identical list continues
}
```

#### 2. The "Labyrinth" Copy (Deobfuscated)
*Decompiled by Nigginality Research Team*
```lua
local v_u2 = {
    ["__index"] = function(_, arg2)
        v_u1("__index", arg2) -- Calls internal check
        return nil
    end,
    ["__newindex"] = function(_, arg2, arg3)
        v_u1("__newindex", arg2, arg3)
    end,
    -- ...
    ["__ad"] = function(arg1, arg2)  -- LOOK: They just abbreviated "__add" to "__ad"!
        v_u1("__ad", arg1, arg2)
        return nil
    end,
    ["__su"] = function(arg1, arg2)  -- "__sub" became "__su"
        v_u1("__su", arg1, arg2)
        return nil
    end
}
```

> [!IMPORTANT]
> **Minor Modifications, Same Logic**:
> The only difference is what it returns.
> *   **Original**: Returns dummy values like `workspace.__z`.
> *   **Taro's Version**: Calls an internal function `v_u1` (to flag the user) and then returns `nil` (or "U"/"") to crash or confuse the script calling it.
>
> Despite this small change, the **structure is identical**. They simply abbreviated metamethod names (e.g., `__add` -> `__ad`) and wrapped it in base64 strings to hide the source. **This is a direct paste.**

---

## Community Verdict: "Garbage"
The DevForum community warned everyone this code was bad *before* Taro pasted it.

> "Bad outdated detection... this would only flag the very small minority on pastesploits"
> — **LittleDyingDuck**

> "Any competent exploit... has this patched. Only pasted exploits that suck horribly are vulnerable"
> — **packpngtexture**

Even the **original author** admitted it:
> "Modern exploits (Wave, Zenith): 0% detection... Free exploit (bunni.lol): Completely immune"
> — **Test_server1** (Original Author)

---

## For Taro (aka Devforum Slop)
"The audacity to call me 'AI slop' is almost cute. It's especially rich coming from someone whose 'pasted anti-cheat' I just waltzed through. Now you're over there, getting publicly flamed by the very 'slop' you tried to dismiss. I'd say you've been slandered like a fucking extracurricular your own resume forgot to mention—utterly irrelevant and completely beneath notice."

*   **Copied** code known to be ineffective.
*   **Obfuscated** it to claim it was original.
*   **Ignored** 4 months of reports.
*   **Banned** those who tried to help.

The "Labyrinth" is a lie. It's a pasted maze with no walls.

---

![caption](https://cdn.discordapp.com/attachments/1057372474246975549/1463219151811383498/caption.gif?ex=6975a5c7&is=69745447&hm=8c438b38cb975e46555f32cabf971a4fc2674b2e7476278612993d7bade755a0&)

## NIGGINALITY HUB
**The Premier Community for Grave Digger & Decaying Winter Exploits**
We develop the best exploits for both games, with features that completely bypass Labyrinth's ineffective anti-cheat.

### Features
✅ Full Labyrinth bypass
✅ Undetectable exploits
✅ Regular updates
✅ Active community

### Owner
**Resolver** (`x2omarxs`)
User ID: `923300723662393454`

### Join Us
**Discord Invite Links:**
*   [discord.gg/Fzj2C8fux8](https://discord.gg/Fzj2C8fux8)
*   [discord.gg/GhwYCucv4z](https://discord.gg/GhwYCucv4z)
*   [discord.gg/bSmjPXWjrU](https://discord.gg/bSmjPXWjrU)
*   [discord.gg/eHAh8bbZYS](https://discord.gg/eHAh8bbZYS)
*   [discord.gg/gbZa6Pbv4P](https://discord.gg/gbZa6Pbv4P)

### Sources & Credits
*   **DevForum Post**: [Detection of ALMOST ANY hookmetamethod...](https://devforum.roblox.com/t/detection-of-almost-any-hookmetamethod-and-getrawmetatable-exploits/3847679)
*   **Discord Transcript**: [Ticket View 5035](https://dashboard.tickets.bot/manage/1255891838833786960/transcripts/view/5035)
*   **Game Links**:
    *   **Grave Digger**: [Grave Digger](https://www.roblox.com/games/18259975825/Grave-Digger)
    *   **Decaying Winter**: [Decaying Winter](https://www.roblox.com/games/13438553315/Decaying-Winter)

*Document compiled by Resolver & Reign*
*Exclusively released at Nigginality Hub*
*hharley: Game Manager (ID: 572027926833528833)*

 All sources are public and verifiable. All timestamps are accurate. All code is real.
 This exposé represents 4 months of research. Every claim is backed by evidence.
