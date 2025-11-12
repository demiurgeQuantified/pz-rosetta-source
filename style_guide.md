# Project Style Guide
Style guide for contributions to this project. This document is currently WIP.
### Functions
Notes for a function should describe what it does, or in the case of a callback, what it should do.
Notes for parameters and return values should describe purpose as well as units, range, meaning of
specific values, etc. They should not start with articles such as 'the', 'a', etc.
If there is nothing to remark about a parameter or return value that is not already included in the 
function notes, it may have no notes.

Parameter names should be only one word if possible, and written in
lower camel case if not. Parameter names should indicate purpose if possible (e.g. `doAttack(attacker)`
is preferred over `doAttack(player)`)
```yml
- name: getPlayerHealth
  parameters:
  - name: player
    type: 
      full: zombie.characters.IsoPlayer
    # No notes because it is obvious from the function description that this player's
    #  health will be retrieved, and there is nothing else to say about it
  return:
  - name: health
    type:
      full: number
    # Not 'The player's'
    notes: Player's health between 0 and 100.
  # Overview of the function: This could be very detailed for complex functions,
  #  but it should not go into detail about the specifics of the parameters or return value(s).
  notes: Returns a player's health.
```
### Events
Prefer the term 'trigger' over similar terms (e.g. 'fire') as it is the terminology used by the game. For the same reason, 'callback' should be preferred over 'listener'.
