# ChessPersonality

## Problems:
- How to run deep analysis fast?
<br>

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

Traits:

- often held in high regard by chess fans due to entertaining and inventive playstyle
- courageous, risky style 
- inventive ideas may occasionally backfire
- few have reached the very top
- good feeling for initiative, for which they might sacrifice material
- sharp combinative vision
- strong sense of trade-off between material and initiative (intuitive talent)
- calculate variations well
- strong at blitz and rapid and other faster time controls
- not afraid to make non-conventional moves
- 

  
Players of this kind: Anand, Shirov, Morozevich


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



## Ideas for implementation:
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
  - best vs second/third move difference, with various depths

## Selected Features
  - number of mistakes, blunders, inaccuracies -> quality of play
  - first inaccuracy,mistake,blunder - game deciding moment (the game doesnt turn around after)
  - engine eval average, median, min, max (CP)
  - Cp delta average, median, min, max
  - material imbalance (average, longest) -> could indicate initiative
  - development imbalance(avg, min, max, median) -> make it first 20 moves only!
  - mobility imbalance()
  - control imbalance
  - tension,safety: tendencies (1-10, 11-20, 20-30, 31-40 etc. avg. )
  - critical moment (which move), any characteristics for this(e.g. space, king safety, mobility, )?
  - first+last inaccuracy, mistake, blunder
  - avg cp delta
  - was the suggested move with the same piece?
  - only move? if not, was the correct piece moved?
  - number of times each piece was moved (do something with early trades)
  - opening + statistics (e.g. from chessgames.com)
  - attackers, surprise-moves (optional, only if i have a lot of time)

## Benchmarks 

Without any data data cleaning, feature engineering etc. I selected ~50 games totrain my first model. <br>
I've used fastai's tabular data model and xgboost to have a benchmark result.<br>

Fastai Tabular | XGBoost
------------ | -------------
33% | 16%

## Improvements were needed everywhere ( ~ halfway through the semester)

After 200 data samples I still struggled to reach a decent performance, so I decided to automate my game evaluation pipeline.
I choose a relatively big pgn chess database, moved it to a SQL database, and queried the games of my "example players".

This change probably won't help me out as much as I want it to, so I need to have additional quality features as well. 
In order to solve this problem I asked a teammate of mine. He recommended features that I have not considered before. 
We'll see how much it helps!

Added features: how long until the player loses a worse position, how long until the player wins a better position, vegjatek mikor (vezerek mikor tunnek el a tablarol), gyaloglepesek % 

My mentor also helped me tremendously with getting a stronger computer on our university cloud in order to solve the computational problems, as I wanted to analyze the games deeper, because I believe it might help me a great deal. 
