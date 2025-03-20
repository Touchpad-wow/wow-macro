# Warrior macros

As a warrior it's a good idea to have some form of `/startattack` in each of your macros to make sure you're not just standing there looking silly.
Basic macros could look something like this

```
/startattack
/cast Heroics Strike
```

Where you use an ability, in this case Heroic Strike, and you also make sure to auto attack.
This type of macro should be used with pretty much every ability for a warrior.

- [Warrior macros](#warrior-macros)
  - [Berserker Rage](#berserker-rage)
    - [Change stance and use](#change-stance-and-use)
  - [Charge](#charge)
    - [Always charge](#always-charge)
    - [Charge or Overpower](#charge-or-overpower)
  - [Weapon swap](#weapon-swap)
    - [Ooh shit button](#ooh-shit-button)
    - [Ooh shit button, advanced version](#ooh-shit-button-advanced-version)

## Berserker Rage

### Change stance and use

Because Berserker Rage can only be used in Berserker Stance,
this macro will change your stance into Berserker Stance unless you're already in that stance
and then cast Berserker Rage.

```
#showtooltip Berserker Rage
/startattack
/cast [nostance:3] Berserker Stance
/cast Berserker Rage
```

## Charge

### Always charge

Since Charge is an ability that cannot be used while in combat we need to use Intercept instead if we are in combat. This macro therefore uses Charge if you're not in combat and Intercept if you are in combat, making sure that you'll always be able to charge.

```
#showtooltip [nocombat] Charge; Intercept
/startattack
/cast [nocombat, nostance:1] Battle Stance; [combat, nostance:3] Berserker Stance
/cast [nocombat] Charge; Intercept
```

### Charge or Overpower

Since you can't use Charge while in combat this macro lets you use Charge if you're not in combat and Overpower if you are in combat.

```
#showtooltip [nocombat] Charge; Overpower
/startattack
/cast [nostance:1] Battle Stance
/cast [nocombat] Charge; Overpower
```

## Weapon swap

When doing macros using items you will need to add the exact name of the item you want to use.
The easiest way to do this is to open the macro you want to edit, place the cursor where you want the item name to be
and then Shift click on the item in your inventory.
In the macros below replace whatever is within the quotation marks (including the quotation marks) with whatever item you want there.

### Ooh shit button

This is your "omg I'm going to die"-button, it equips your shield and your tanking weapon.
After that it will cast Shield Wall and yell out an informative message to let the group know.

```
/stopcasting
/cast [nostance:2] Defensive Stance
/equipslot 17 "name of your shield"
/equipslot 16 "name of tanking weapon"
/cast Shield Block
/yell I'm now a wall!
```

### Ooh shit button, advanced version

This macro does the same as the one above if you don't have a shield equipped.
If you have a shield equipped this macro will change to the other weapon setup.
This macro is great for switching between tanking weapons and dps weapons.

```
/stopcasting
/cast [nostance:2, noequipped:Shield] Defensive Stance
/equipslot [noequipped:Shield] 17 "name of your shield"; "your regular offhand weapon"
/equipslot [noequipped:Shield] 16 "name of tanking weapon"; "your regular main hand weapon"
/cast Shield Block
/yell I'm now a wall!
```