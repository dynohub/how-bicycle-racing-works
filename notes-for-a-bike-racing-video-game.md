how-bicycle-racing-works/notes-for-a-bike-racing-video-game.md
Last modified: 2022-12-31 16:39

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
		* Turn-based games capture this well. A turn-based bike racing game might be insane... but awesome? 


## What does it look like
* an ascii character for each rider.
	* (look through unicode characters and see if there's one that would be a good top-down bike racer)
* teams are indicated by colors.
* A peloton controlled by flock modeling mechanics maybe.
* terrain and wind speed/direction are indicated somehow


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
* a more advanced version might have wind speed affect battery drain, or direction creating echelons.


## How does it play
* you can give racers orders to try and achieve a breakaway. 
	* they make an attempt, but opposing teams might try to go with it, or shut it down.
* The riders may not do what you order -- they might have some autonomy.

