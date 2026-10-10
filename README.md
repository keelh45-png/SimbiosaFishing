# SimbiosaFishing — GitHub Actions build draft

This is an **untested WIP**. GitHub Actions is configured to try building it and upload the resulting JAR as an artifact.

## Build it on GitHub
1. Create a new GitHub repository (for example `SimbiosaFishing`).
2. Upload/push the **contents of this project folder** to the repository root. Make sure `.github/workflows/build.yml` is included.
3. Open the repository's **Actions** tab and select **Build SimbiosaFishing**. Run it with **Run workflow**, or push a commit to trigger it.
4. If the run succeeds, open the completed workflow run and download **SimbiosaFishing-JAR** under Artifacts. The JAR inside is the file to test in a staging server's `plugins/` folder.
5. If it fails, open the failed step and send the error log so we can fix it.

## Important
- This workflow does **not** prove compatibility until the build succeeds and the JAR is tested on the actual Paper 26.2 server.
- The Paper API dependency uses `26.2.build.+`; if Paper's Maven repository does not resolve that selector, replace it with a published Paper API version for the target server.
- This source has not yet been compiled or tested. Gameplay features are incomplete; read the limitations below before testing.

## Included in this source draft
- 30 fish definitions, 5 rod definitions, 5 bait definitions in YAML.
- `/fish` starter GUI, `/fish collection`, `/fish stats` placeholder, `/fish sellall`, `/fish sell confirm`, `/fish sell cancel`.
- Optional Vault economy integration and configurable rarity broadcasts.
- `/fishadmin reload`, `/fishadmin test <RARITY> <fish name>`, `/fishadmin give <player> <fish|rod|bait> <id>`.
- Permission prefix `simbiosafish.*` and PDC item identity tags.
- Bait requirement/consumption intended for successful custom catches, with `simbiosafish.bypass.bait` bypass.

## Known WIP limitations
- Rod/bait shop buttons and bonus effects are not complete.
- No persistent statistics, quests, database leaderboard, custom resource-pack model wiring, or Geyser mapping.
- Not yet verified on Paper 26.2. Test on a backup/staging server, not a live production server.
