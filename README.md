# lisy35_stern_pinball_v2
New game rules for Stern Pinball

# Thoughts on MPF
The following are some of my thoughts on using MPF to develop a game.  Please don't interpret these as corrcet or inline with the intent of the MPF framework.  These are more my own musings on what I think of using MPF. 

## Programming with MPF
It's best to think of the framework and the YAML configuraiton as it's own pinball domain specific lanaguage (DSL) but since it's not a true language with it's own semantics it's often difficult to see problems introduced during development.  There's a lot of run-time testing/debugging required to verify a game is working correctly.  There is a language server implementation that plugs into VSCode which does provide some semantic checking but I've found it to be a bit unreliable.  Also some of the concepts configured in the YAML seem quite awkward to anyone used to using a general perpose programming language, e.g. Typescript, C++, Python.  This is more of an issue with the limitations of being tied to the YAML syntax.  I think defing an actual DSL would go long way to aleviating this.   

Building your game in MPF is declarative and closely related to functional programming.  In that sense you shouldn't be modifying state very often.  In fact the declarative nature of YAML and the framework implemented by MPF often makes this diffuclt.  For example there are not explict ways do declare funcitons.  In practical terms you should avoid modifying external state, e.g. adding player varables to track some kind of execution state within a mode.  State is often modifed as a recation to an event or explict event that's meant to update a global varaiable, e.g. score_100 event might add 100 to the current player's score.  



# Issues
* (bug) able to collect 50k a second time
* (feature) bonus should go beyond 100k(?)
* (feature) Rollovers should score 10 & ring the 10k chime when advancing bonus
* (feature) Enable lite tripple bonus collect