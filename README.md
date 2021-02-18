# ChessPersonality

## Introduction
The general idea of my project is to differentiate chess styles and personalities, as it might be useful to predict the outcomes of the games.<br>
Was this hipothesis true, the consequences could be immense. Previously coaches and players had not spent huge amount of time thinking about preparation in this way, but these styles might turn out to be more important than we initially thought. <br>

Though we must mention, that the popular conception (just like what Rowson thought) is considered to imply that the importance of whether a move is "aggressive", "solid", "attacking, "defensive", "logical" or something else is little compared to whether a move is GOOD or not! Just like the engines think nowadays, you either make good moves or not, the reasons for that hardly matters. 
Lars Bo Hansen in his book, "Foundations of Chess Strategy" wrote the following on this topic: 

> ... top players today are much more universal than in the past. This
> is because of the trend in chess towards faster time-limits and the
> more and more concrete nature of top chess, where the stakes in the
> form of top-notch opening prepaartion and concrete calculations are
> rising rapidly with the introduction of computer aids in analysis and
> preparation. Today you cannot become a real top player 'just' by being
> a strong theoretist (or any of the other types) - you still need to
> work on areas that characterize the other types.

However, we must realize that playing out different kinds of positions between the same players can impact the results more than we might have thought. This experiment of mine is aimed to clear the air in this regard. <br>

~~LBH argues in his aforementioned book that nowadays people struggle to play all kinds of chess positions equally well, even though it was considered to be a neccessity in the past. <br>~~ 
He went on to categorize chess players into 4 different groups: 
  - [Activists](#activists)
  - [Reflectors](#reflectors)
  - [Pragmatists](#pragmatists)
  - [Theorists](#theorists)
  
|                |Facts|General Concepts|
|----------------|-------------------------------|-----------------------------|
|Intuition|Activists ("Trial and error")          |Reflectors ("Alternatives")            |
|Logic          |Pragmatists ("What must be done must be done..")            |Theorists ("A model for everything") 

<br>
*source:http://www.qualitychess.co.uk/blog/1841*
  
I will move on to show what he thinks the recognizable traits of each category are. I will also add my ideas on what I think help us to classify a player into that group. 

## Activists

## Reflectors

Traits:

- very good at sensing and collecting small advantages
- often very strong in endgames 
- good at assessing the values of long term positional sacrifices 
- calculate relatively few variations and make moves on general concepts, trying to utilize their undestranding
- great feel for the pieces even in unknown positions
- tendency for sloppy opening play or oversight (calculate relatively few variations)
- might have troubles when playing forcing positions (or when detail-heavy positions arise)
- opponents of reflectors might underestimate ideas

  
Players of this kind: Capablanca, Smyslov, Rubinstein, Petrosian, Karpov, Adams, Carlsen

### Theorists

Traits:
  - great understanding of pawn structures and how they affect the play
  - strong in closed and semi-closed positions (good manoeuvring)
  - often very great at utilizing the bishop pair
  - proceedings in the game are often logical and very systematic (like following a thread)
  - good and thorough in opening prep
  - usually plays some kind of system, ideal for playing the same opening for longer time (instead of changing it frequently)
  - stubborn in the belief of their system
  - struggles if the logical thread is broken (when positions with 'no logic' arise, concrete evaluation is needed, sharp opening)
  
Players of this kind: Steinitz, Tarrasch, Nimzowitsch, Botvinik, Kramnik, Leko

Illustrative games: ...

## Pragmatists

Traits:

- most common type of world champions
- open-minded learners, who who can identify and learn new concepts rapidly
- concrete, fact-based decision making
- strong and accurate in the calculation of variations
- strong & precise opening prep (often playing sharp variations)
- often trend-setters with their opening-play
- strong attackers with a great intuition for direct attacks on the king (the preparation of the attack might be just as important)
- sometimes lose the thread in 'dull' or simple positions
- excel is sharp positions
- against pragmatists: go for boring and technical positions

  
Players of this kind: Alekhine, Euwe, Keres, Fischer, Korchnoi, Kasparov, Svidler, Topalov



Ideas for implementation:
  - https://github.com/mptedesco/python-chess-analysis (in depth game analysis)
  - https://github.com/CYHSM/chess-surprise-analysis (chess surprise analysis, how "deep"/surprising a move is)
  - https://github.com/MGleason1/PGN-Spy (originally made as an anti-cheat, but could be useful)
  - count how many times each piece moved and compare it to the number of moves (more pawn moves -> probably attacking)
  - when do pawn moves happen (already has space advantage or no)
  - space advantage
  - inaccuracies, how big are they
  - how many blunders, inaccuracies etc. (when did they occur)
  - suggested move (what piece), what piece did he move instead, is it an intermezzo (how do i check that?)
  - opening type (open,closed,semi-closed etc.)
  - quality of play when losing vs winning
  - best vs worst move difference
  





