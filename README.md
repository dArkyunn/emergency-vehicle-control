
# More Immersive Emergency Lights for RageMP

A script for GTA V's multiplayer modification RageMP, that adds more immersive controls of emergency lights and sirens for default, or non-els vehicles. Both lights and sirens are synchronized between players!

##### Table of contents

1. [Installation](#Installation)
2. [Usage](#Usage)
    * [Default keybinds](#Default-keybinds)
    * [General information](#General-information)
3. [Customization](#Customization)
    * [Keybinds](#Keybinds)
    * [Siren and horn tones](#Siren-and-horn-tones)

## Installation

1. Put **_more-immersive-emergency-lights-server_** into your **/packages/** folder.
2. Put **_more-immersive-emergency-lights-client_** into your **/client_packages/** folder, and add the line `require('more-immersive-emergency-lights-client/index')` into your **/client_packages/index.js** file.
3. Done!

## Usage

### Default keybinds

(You can change those in your **_more-immersive-emergency-lights-client/index.js_** file.)

* *Q* - Goes up a lightning stage
* *Ctrl+Q* - Goes down a lightning stage
* *E* - Horn
* *1* - Toggles siren tone 1
* *2* - Toggles siren tone 2
* *3* - Toggles siren tone 3
* *4* - Toggles siren tone 4
* *5* - Toggles random siren every 5 seconds
* *6* - Toggles auxiliary siren

Default timeout for every key is 350ms. You can change that (see [Customization#Keybinds](#Keybinds) section).

### General information

There are **3** lightning stages

* *Stage 1* - No lights and sirens
* *Stage 2* - Only lights
* *Stage 3* - Lights with capability to toggle sirens

You can move freely between stages using *Q* and *Ctrl*Q*.

When going from *Stage 3* down to *Stage 2* your sirens will automatically get toggled off.

If you press *E* in any stage, you will use your horn.

Auxiliary siren is independent of the primary one, as such, it plays it's own tone, and can be turned on and off independently of the primary siren. \
Default tone for auxiliary siren is the same as tone 1. You can change that (see [Customization](#Customization) section).

## Customization

### Keybinds

You can change your keybinds in this block:

```Javascript
const keybindsVK = {
    Stage: 81, // Light stage modifier
    Tone1: 49, // Siren tone 1
    Tone2: 50, // Siren tone 2
    Tone3: 51, // Siren tone 3
    Tone4: 52, // Siren tone 4
    Tone5: 53, // Random siren tone every 5 seconds
    Tone6: 54, // Auxiliary siren (tone 1)
}
const keybindsControls = {
    Horn: [13, 51] // Horn
}
```

1. *keybindsVK* - Here, you can set a preferred key for an action via a **virtual keycode**. [Here](https://docs.microsoft.com/en-us/windows/desktop/inputdev/virtual-key-codes) is a list of **virtual keycodes**.
2. *keybindsControls* - Here, you can set a preferred key for an action via a RageMP **input group and control** combo. First number is the **input group** (usually 0, 1 or 2 should work), while the second number is the **control**. [Here](https://wiki.rage.mp/index.php?title=InputGroup) is a list of **input groups**, and [here](https://wiki.rage.mp/index.php?title=Controls) is a list of **controls**.

To change the keybinds' timeout, change the number in this line:

```Javascript
const keyTimeout = 350 // Milliseconds
```

### Siren and horn tones

You can change siren and horn tones in this block:

```Javascript
const sirenTones = {
    tone1: 'VEHICLES_HORNS_SIREN_1', // Siren tone 1
    tone2: 'VEHICLES_HORNS_SIREN_2', // Siren tone 2
    tone3: 'VEHICLES_HORNS_POLICE_WARNING', // Siren tone 3
    tone4: 'VEHICLES_HORNS_AMBULANCE_WARNING', // Siren tone 4
    aux: 'VEHICLES_HORNS_SIREN_1', // Auxiliary Siren
    horn: 'SIRENS_AIRHORN' // Horn
}
```

* *tone1* - changes the sound for siren tone 1.
* *tone2* - changes the sound for siren tone 2.
* *tone3* - changes the sound for siren tone 3.
* *tone4* - changes the sound for siren tone 4.
* *aux* - changes the sound for auxiliary siren.
* *horn* - changes the sound for horn.

## Contribution

1. If you think something could be done **better** - create a [pull request](./pulls) with your code, and additionaly create an [issue](./issues) explaining why it is better.
2. If you've found a **bug** - create an [issue](./issues) using the given template.
