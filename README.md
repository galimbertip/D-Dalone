# D&D Alone

Play Dungeons & Dragons 5e on your own, in the browser. Claude is the Dungeon Master and also plays your three party companions. The dice are rolled by the app, so nobody can cheat.

**Play:** https://galimbertip.github.io/D-Dalone/

## What it does

- **Setting:** write your own, pick a preset (Brianza 1176, Fantasy classico, Laguna veneta gotica), or roll the d20 to generate a random one.
- **Guided character creation:** stock, class, ability scores (standard array or 4d6), background, skills and four questions about your backstory.
- **Hidden campaign:** before play starts, the DM writes the whole adventure (plot, villain, acts, NPCs, clues, encounters, endings) and keeps it from you. It also creates three companions that cover what your class lacks.
- **Game table:**
  - The DM narrates and asks for rolls, and you press "Tira".
  - The app works out bonuses from your sheet, rolls damage and applies the damage the party takes.
  - Companion and enemy rolls happen on their own.
- **Long-term memory:** a campaign journal, experience points and levelling up.
- **Saves:** automatic, in your browser. Use "Esporta campagne" / "Importa campagne" to move a campaign between devices, for example from the PC to the work laptop.

## What you need

An **Anthropic API key**. Create it at [console.anthropic.com](https://console.anthropic.com/settings/keys) under API Keys, then paste it in the app's **Impostazioni**.

- The key is stored only in your browser and is sent only to `api.anthropic.com`.
- Don't use it on shared computers. If in doubt, revoke it from the console.
- Pay-as-you-go cost: generating a campaign uses the most capable model; each turn uses the model you pick (Rapido, Bilanciato or Profondo). The rules sent with every turn are cached, so long sessions cost less.

## Technical notes

- A single static page (`index.html`), with no build step and no dependencies.
- Rules based on the SRD 5.1 (Creative Commons licence).
- The DM replies in structured JSON: narration, requested rolls, state changes, scene, XP, journal, suggested choices. The app is the source of truth for HP, spell slots, inventory and conditions.
- Opened as a Claude artifact, the same page uses the built-in Claude and saves to your account, with no key needed.

## Publishing on GitHub Pages

Settings → Pages → Source: *Deploy from a branch* → branch `main`, folder `/ (root)`.
