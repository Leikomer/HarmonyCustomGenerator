# Guide will be updated  
**Last updated:** 07.06.2025  

---

## Creating a Custom Monument

1. Open **RustEdit**.  
2. Load or build your monument.  
3. If the monument is fully custom (does not contain the original monument) — add a **SpawnPoint** at coordinates **(0, 0, 0)**, or see below.  
   - 3.1. In this case, the **SpawnPoint** is the **CENTER OF THE ORIGINAL MONUMENT**; if it’s placed incorrectly, the custom monument will be misaligned.  
   - 3.1.1. For example, the center of a gas station is located below the monument itself because of a cave, so you need to raise the monument (examples are in the attached files). If you don’t do this, your gas station or custom monument will be sunk into the terrain.  
4. Make sure that the **SpawnPoint** or the **original monument** is the **first object in the hierarchy**.  
5. Save the **.map** file under the correct name.  

---

## Important

The file must be named exactly like this:  
```
<monument_name>.prefab.map
```

**Examples:**  
```
fishing_village_a.prefab.map  
harbor_1.prefab.map
```

---

## Where to put the .map

Move the `.map` file to the folder:  
```
/maps/prefabs/
```

---

## Enabling Swap

Open **HarmonyCustomGenerator.json** and edit the following:  
```json
"SwapMonuments": {  
  "Enabled": true  
}
```

This enables automatic monument swapping during map generation.

---

## How Swap Works

During map generation:
1. It looks for a monument with a matching name (`*.prefab`)
2. If a `.map` file with that name is found → it replaces the original
3. The original’s position, height, and rotation are preserved

Important: the generator does not recreate roads and surroundings, so already connected roads and terrain from the old monument remain unchanged.

Two versions of the map will be created:
- with swaps  
- without swaps (if enabled)  

---

## Troubleshooting

If the monument does not appear or is distorted, check:

- Is the `.map` file named correctly?  
- Fully custom monument — double-check **SpawnPoint positioning rules**.  
- Is **SpawnPoint** or the **original monument** not first in the hierarchy?  
- Is the `.map` file not located in `/maps/prefabs/`?  
- Is `SwapMonuments.Enabled` not enabled in the config?  

---

### Examples of full custom monuments
*(see files in /Examples/prefabs/)*
