## What works? Is quest X implemented?

[What Works?](What-Works)

## How can I help the project?

[How can I help?](How-Can-I-Help)

## Where can I find servers to play on?

Final Fantasy XI Private Servers Community [Discord](https://discordapp.com/invite/msACzWV) & [Reddit](https://www.reddit.com/r/FFXIPrivateServers/)

## Is there a GM command that does X?

All available GM commands, with descriptions and the level of GM they require, can be found [here](https://github.com/LandSandBoat/server/tree/base/scripts/commands).

## When will feature X arrive?

We practice [clean room engineering](https://en.wikipedia.org/wiki/Clean_room_design), which means we have to implement everything from scratch. As such, progress is slow. We are also trying to balance feature development, bugfixes, performance improvements, exploit resolution, code review, and testing.

## Can I use Trust: X, why doesn't Trust: Y do anything?

Go check their status [here](Trusts).

## Can I pay someone to implement feature X?

We will never accept financial or material incentives for our work. This is a hobby project. External incentives would drive developer and staff time in a way that makes it no longer a hobby.

## The code for feature X is available in the community, why haven't you taken it?

Features in LandSandBoat are those that have been submitted to us, meet our standards for quality and accuracy, and that we have had the time to review and integrate with the rest of the codebase. It is very rare that we will accept code on someone else's behalf. While there is technically nothing stopping us, it would undermine our position in the community.

Similarly, sending us code snippets creates more work and strain on staff and developers. If you have code you want to contribute, please speak to us with GitHub Issues, Discussions, and open a Pull Request.

## When can I play "Classic" Dynamis?

You can't - it isn't in the game anymore.

<details>
<summary>Read more</summary>
<p>

"Classic" Dynamis was removed from the game in 2011. The spawn mechanisms as you remember them are gone from the game, and those zones no longer act the way they used to.
The overall project goal is to emulate the retail game as closely as possible, so a massive custom solution to approximate "Classic" Dynamis is not on our roadmap.

However, in 2017 Dynamis Divergence was released, a content level 149 version of the "Classic" Dynamis players wanted to experience again.

If we were to support a custom Dynamis solution, it would be the implementation of Dynamis Divergence and a set of mods or switches that scale it down to level 75 era difficulty.

Keep in mind that we haven't completed all content up to 2007, so a full implementation of content from 2017 with mods on top isn't coming any time soon.

</p>
</details>

## Can I change job X to play like job Y?

No.

<details>
<summary>Read more</summary>
<p>

There are _many many_ things are enforced by the game client.

For instance; you can set your jobs to be 75NIN/75BLM but you won't be able to equip Lv75 BLM gear - this is enforced by the client.

Bypassing these restrictions would need heavy client modification (which we don't support) or support scripts and changes in core.

</p>
</details>

## Why isn't Yell/Trust/Auction House etc. available in every zone?

What's available to use per-zone is controlled with the `misc` flags column in `zone_settings.sql`. These flags correspond to the `ZONEMISC` enum in `zone.h`. A query to modify those flags can be found in [Useful SQL queries](Useful-SQL-queries#enable-zonemisc-features-everywhere).

<details>
<summary>Read more</summary>
<p>

```cpp
enum ZONEMISC
{
    MISC_NONE       = 0x0000,   // Able to be used in any area
    MISC_ESCAPE     = 0x0001,   // Ability to use Escape Spell
    MISC_FELLOW     = 0x0002,   // Ability to summon Fellow NPC
    MISC_MOUNT      = 0x0004,   // Ability to use Chocobos and mounts
    MISC_MAZURKA    = 0x0008,   // Ability to use Mazurka Spell
    MISC_TRACTOR    = 0x0010,   // Ability to use Tractor Spell
    MISC_MOGMENU    = 0x0020,   // Ability to communicate with Nomad Moogle (menu access mog house)
    MISC_COSTUME    = 0x0040,   // Ability to use a Costumes
    MISC_PET        = 0x0080,   // Ability to summon Pets
    MISC_TREASURE   = 0x0100,   // Presence in the global zone TreasurePool
    MISC_AH         = 0x0200,   // Ability to use the auction house
    MISC_YELL       = 0x0400    // Send and receive /yell commands
};
```

</p>
</details>

## What is Darkstar Project (DSP), Project Topaz (TPZ), or Topaz Next (TPZN)?

These are the predecessor projects that LandSandBoat is derived from, which are archived and no longer maintained or supported.

## Why is the airship in Sauromugue Champaign skidding along the ground like a land speeder?

It's a feature, not a bug. 👀
