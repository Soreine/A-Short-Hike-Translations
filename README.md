# A Short Hike: Unofficial Translations
Resources to make or install unofficial translations for the game "A Short Hike"

More information can be found here: https://a-short-hike.fandom.com/wiki/Unofficial_Translations

## Writing your own translation

A tutorial on how to write your own translation will be made available here shortly. It mainly consists of translating all the texts in the main text asset of the game. You can find a readable version of this file as [MountainQuest.yarn](https://raw.githubusercontent.com/Soreine/A-Short-Hike-Translations/master/MountainQuest.yarn).

I have yet to find the asset for the game menus, the fishing book,the  treasure map, and other items description.

### Structure of MountainQuest.yarn

The different pieces of texts (a given dialogue with a Non Player Character (NPC), reading a sign, etc.) are preceded by `===` and a title and other metadata, like so: 

```
===
title: ThoughtsStart
tags: 
colorID: 0
position: 3342,3296
---
I'm very shy and sad :(
Sometimes I see cool people I recognize from the internet but i'm too afraid to say anything so I say nothing.
===
```

They are listed in complete disorder. So you will have to guess the context using the metadata.

Some dialogue have branching options and other scripting, depending on the advancement of the player for example. All these scripting information are put inside double brackets like  `<<...>>` or  `[[...]]`. The text inside the brackets should not be translated, it's code essentially.

Let's make sense of an example:

```
===
title: AuntIntroStart
tags: 
colorID: 0
position: 4164,-2635
---
hey how's it going?
i haven't seen you all day
you been busy?
<<SetSpeaker Player>>
uh, kinda
well, not really
i've just been waiting\naround for a call
[[AuntIntroEnd]]
```

The `title` helps us understand this is the first part of the dialogue with the Aunt, at the start of the game.
After the `---` is the beginning of the spoken by the Aunt.
Each line corresponds to a dialogue bubble in the game, this means the player must press a button after reading `hey how's it going?`
Some bubbles are long and need to have line breaks to be displayed correctly, these actual line breaks are represented by `\n`, like in the line `i've just been waiting\naround for a call`
Whenenever the player (Claire) starts talking, it is indicated with `<<SetSpeaker Player>>`. When the speech is back to the NPC or object, it is indicated with `<<SetSpeaker Original>>`.
Sometimes, a dialogue will lead to another. This is done with a reference to its title, like so `[[AuntIntroEnd]]`.

## Making a translation patch

Instructions will be given here on how to make a patch for the game containing the translated texts.
