# Requirements 
The purpose of this document is to outline the changes the new ruleset (dark north) makes to the original ruleset (dnd 5e). 

[Dark North Ruleset](./Dark-North-Comp-1_2.pdf)

## Preamble
The purpose of this repository is to modify the dungeons and dragons fifth edition ruleset to be inline with the rules detailed in the Dark North pdf linked above. This is a somewhat daunting task as it adds new rules and values that have to be appended to existing items. One such example is that weapons now must have a weight classification which, depending on the size of an actor, may or may not impose disadvantage to use. 

As this is the first large scale project that I am attepting to do, I imagine that this will take me a considerable amount of time due to my schooling, my work, and of course my sanity. Much of what I have read so far in the pdf is very cool and interesting to me however, so I am excited and passionate about the project. 

Since I have the luxury of using the dnd5e system as starter code, I am hopefull that most of the development will be simply edditing the files so that they are compatable with the new ruleset. However since most of the rules implement a new layer or layers of complexity I will likely be revising some the logic of some things. 

---

## Purpose
The purpose of this document is not to lay out the design of the new ruleset. This document is to help the developer (me) have a cohesive description of the many changes made to the original 5e rules so that I know what methods and yml files need to be refactored. In the latter parts of the document I will outline more about the locations of the files needing to be changed, and outline what the changes are intended to achive. Returning to the example in the preamble, I will need to add a new identifier to various weapons in the yml files to include the weight classification of the weapon, and then create a new function that will determine how the weapon will function for the actor. example:
```
if actor.race.size == "small" && weapon.type.weight == "heavy" && [actor.class.feat || actor.general.feat] !== "heavy weapon training":
    return disadvantage
```
this pesudocode represents an if comparitor that checks if the actors race has the small attribute and the weapon has the heavy trait and the actor does not have any feats that include some sort of weapon training, then it imposes disadvantage on the actors attack with said weapon. 