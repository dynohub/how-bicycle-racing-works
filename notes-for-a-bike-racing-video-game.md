how-bicycle-racing-works/notes-for-a-bike-racing-video-game.md
Last modified: 2023-01-01 21:15

# Notes for a bicycle racing video game
* I've been daydreaming about a game like this for ages.
* I don't know where else to put this, so I'm dropping it into this git repo as bonus material.
* Maybe some programmer out there will be interested in picking it up and working with me on it.


## General description: 
* Imagine a top-down view of a bike race.
* Let's say it's in ascii-mode because I like Rogue-likes, but it doesn't have to be. 
* Unlike other racing games where you control an individual rider, (at least I assume, I've never played them) here you just give orders as the coach.
* Unlike other games (again, assuming here) the *slow* drawn-out drama of bike racing
	* Like the old Atari game Maze;
	* where you see your teams impending doom or victory ahead of of it actually happening, and there's nothing you can do about it but watch and hope it either goes or doesn't go the way it seems like it will.
	* not "slow" in that it takes forever to play, (it might be set up to play out each stage rather quickly actually), but "slow" in the way that it doesn't have faced-pace frenetic shoot-em-up action. Instead it's about setting it up, and giving good orders during the race, and hoping for the best.
* turn based?
	* Turn-based games capture this well. A turn-based bike racing game might be insane... but awesome? 
	* Turn-based could really make the game feel like "chess on wheels" as you use riders like pieces in a chess game (and domestiques like pawns)
	* maybe each turn is a kilometer. You give your orders for the next kilometer and let it play out.
		* In an early version, maybe it just refreshes with the result for that K
		* And later versions animate the riders moving toward that result.
* A proof-of-concept version might be just a sprint stage


## What does it look like
* an ascii character for each rider.
	* (look through unicode characters and see if there's one that would be a good top-down bike racer)
* teams are indicated by colors.
* A peloton controlled by flock modeling mechanics maybe.
* terrain and wind speed/direction are indicated somehow
* See screen concept below


## Team setup
* each racer has strengths and weaknesses. 
* You need to choose a good all-rounder to be your team leader. 
* choose sprinters to try to win flat stages, climbers to win mountain stages.
* make sure you have enough domestiques to keep your team fed and hydrated.
* (Maybe lay out with a points distribution system before the race).


## Stamina: 
* each racer has a certain amount of energy ala the battery metaphor
* in the peloton requires no energy.
* drafting saves significant energy.
* the riders naturally WANT to draft, you maybe have to keep ordering them to attack. (though somehow in a breakaway pacelines form too)
* terrain drains battery faster.
* riders can recover some battery on descents, in the peloton, or eating.
* A rider can't recover ALL of their battery overnight between stages -- so a rider that attacks a lot one day will have less energy the next.
* a mountain climber loses battery less quickly on a mountain than other riders (sprinters lose more quickly)
* a sprinter has a higher top speed in attack mode, but eats up the energy very quickly
	* (all sprinters are faster than average riders by a lot in attack mode, but they are all within a like d6 dice roll of each other for a top speed)


## How does it play
* you can give racers orders to try and achieve a breakaway. 
	* they make an attempt, but opposing teams might try to go with it, or shut it down.
* The riders may not do what you order -- they might have some autonomy.
* A "rider" is an object with stats like:
	* top speed (that is, speed in attack mode)
	* climbing capability (that is, how fast their battery drains on a slope)
	* an awareness of where it is in relation to other riders
* You (as the game player, on your turn if it's turn-based) select a rider, and order them to:
	A. Attack (big energy drain, only lasts for a K, or some set short distance)
	1. pull in front of current group (costs energy)
	2. ride middle of current group (no energy gain or lost)
	3. ride at back of current group (gain moderate battery)
		* with crashes implemented, it's more likely to catch a rider riding in mode 3
	G. (maybe something like this) give up and fall back to the next group back. (bigger battery gain)
		* This would be the mechanism used to have domestiques pick up food an water, if that were implemented. They would G out of the peloton, and then have to 1 and A their way back.
		* Or maybe it's give up for the day, in which case they can have a full battery the next day?
* A rider (or group of riders) will automatically group-up with any other riders they pass (going forward or backward)
* Once in a group, they ride in set 1, 2, or 3 mode until you order them to change.
* A lone rider (they were in attack mode, but that wore off before they could join another group) goes automatically into 1 mode and is a group of 1.
	* (riding by themselves, they cannot be in 2 or 3 mode) 
* The only way out of a group (at least until you add mechanicals, crashes, and bonking) is to attack.
* The peloton is just like any other group, just bigger
* The more riders riding in a group in 1 mode, the faster the group goes


## Example run in sprint stage finish
* You order your domestiques (includes your sprinter lead-outs) and your sprinter specialist to ride in mode 1 at the front of the peloton
* The other teams do likewise, so the peloton is moving very fast.
* You (and the other teams) put your GC rider on 3 mode. (with crashes modeled, you would wait until the final 3 Ks, so no crashes would affect their time)
* The team that has riders in the breakaway orders them all into 1 mode.
	* Riders in the breakaway might try to A attack and get off of the front and go for a solo win -- it would all be about timing and battery. 
* The peloton would (likely) catch the breakaway riders. 
* Some teams try attacks off the front of the all-together peloton now, but that obviously isn't likely to work 
	* (would be cool to have a mechanism with a small chance of it working though!)
* With the finish line in sight (or thereabouts) the domestiques one by one go into attack mode, drain their battery and then you order them back to state 3.
* Then you order the lead-out man into A mode. Then your sprinter.
* If you timed it right, and used your pieces to the best of their abilities, your sprinter will A attack right before the finish line and pass everyone else to win.


## Future features
* multiple stages
* random stats rollups
* a more advanced version might have wind speed affect battery drain, or direction creating echelons.
* model crashes and mechanicals
	* you could imagine a crashed or mechanical rider changing to an x and then having to use attack mode/their battery to catch up to the peloton
* model bonking (a rider with zero battery can limp home, but may be disqualified if they don't have enough speed at limp-rate to make the cut off time) 
	* this would all happen automatically after the race, I think, though it might be cool to see your flatlined rider squeaking in under the cutoff time, or not.
	* could have big implications in a multi-day stage race
* add domestiques capability to bring food and water up to riders (for a batter recharge) but NOT in the final Ks
* doping:
	* you can choose to dope your riders -- but you have to choose riders to dope before the stage start
	* but a rider who wins a stage has like a 1/10 chance of being caught
	* and a rider on the team of the stage winner who is doping has like a 1/20 chance of being caught
	* if you don't win, you don't get caught
* Sprinters fall off the back on mountains
* need to create powerups to keep the game fun
	* maybe "something special" -- a rider with it can double their battery or output for a distance, but then that gets cut in half after they burn out or something.
		* Or, incur an energy debt that has to be paid the next day
	* aerobars
	* newspaper to stuff in jersey for a long descent
* procedurally generated european and colombian names
* a chance that a rider ignores your order ("the rider has switched off their radio! they ignore your order!") 
	* sometimes this could actually result in a win, though maybe at the cost of a rider's energy you were saving for the next stage.


## Screen concept
* Could look something like this:


|          | Rider 1 : Batt:o : 3
|     .    | Rider 2 : Batt:. : 2
|     ..   | Rider 3 : Batt:O : 2
|     ..   | [Rider 4 : Batt:0] : ?
|    [.]   | Rider 5 : Batt:0 : 1
|          | Rider 6 : Batt:o : 1
|          | Rider 7 : Batt:. : 3
|          | Rider 8 : Batt:o : x
|          | Rider 9 : Batt:o : 2
|          | 
|          | 
|          | Selected rider order?
|    ...   |       
|   .....  |     A - Attack
|  ....... |     1 - Front of group (-batt)
|  ......  |     2 - Middle of group
|  ......  |     3 - Read of group (+batt)
|   ....   |     G - Give up
|   ....   | 
|   ...    | 
|    .     | 
|          | 
|          | 
|    xx    | 
|          | 
|          | 


(maybe include profile of stage and representation of where the groups are on the profile down here)
(xx shows crashed riders)
([ ] shows selected rider -- currently last rider in the breakaway -- on your turn you can select each rider and give them an order, obviously you can only select riders on your team)
(Rider stack on right shows their battery status -- in this mockup a scale like this: .oO0 -- and the rider's current order)




