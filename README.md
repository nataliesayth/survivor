# survivor
In progress! I've been using the dataset compiled here: https://www.kaggle.com/datasets/lancetobey/survivor-statistics-dataset

Full citation:

Tobey, Lance. 2024. “Survivor Statistics Dataset.” Kaggle.com. 2024. https://www.kaggle.com/datasets/lancetobey/survivor-statistics-dataset.

I'm still re-organizing and analyzing the data, so any code I've posted is in progress.
I'm also adding S48 data as it airs.

Below is the original README.txt from the creator:

Credit to SurvivorWiki.com for compiling all of the original info I collected. This sped up the process a ton, and as much as I love the show,
1 episode for 1 contestant would have ended this project really fast, and not because I done.

Column Info:

playername - The full name of the player at the time of competiting.

seasonplayed - The specific season the player was on.

age - The age of the player during the season.

occupation - The occupation of the player during the season, specifically what was displayed during confessionals.
If a player was a returning player for a season, the occupation will always be Returning Player.
For Blood v. Water seasons, their occupation will be their partner, and relation to said partner (Ex. Rad's Sister).

hometown - The city and state/provience the contestant lived during the season. This might be changed to seperate city and state/province later.

startingtribe - The tribe the contestant started the season on.

startingtribecolor - The color of the tribe a contestant started on.

timesswapped - The number of tribe swaps a player underwent during a season.

mergetribe - The name of the merge tribe. If the player didn't make the merge, it is listed as No Merge

mergetribecolor - The color of the merge tribe. If the player didn't make the merge, it is listed as N/A

finalplacement - The placement of the player on the season.

votescast - The number of votes a player casted during the season. Ties and any form of extra votes count.

correctlyvoted - The number of times the player voted for who went home. Tie votes and any form of extra votes count.

votesrecieved - The number of votes a player recieved during a season. These include negated votes.

votesnegated - The number of votes a player had against them that were negated.

tribeimmunities - The number of tribal immunites a player won.

individualimmunities - The number of individual immunities a player won at any point in the game.

tribalsattended - The number of tribals a player participated in, meaning they have some chance of voting at the tribal.
Keep in mind that a player can participate and not vote (Safety without Power, Losing a vote, SotD).

advantagesplayed - The number of advantages a player played during the season. If they found an advantage and didn't play it, it does not count.
This is because the editors don't reliably show us all advantages in a season. (Ex. Omar's Idol Nullifier in 42).
** THIS HAS BEEN TAKEN OUT AND WILL BE UPDATED AT A LATER DATE - THIS HAS NOT BEEN DONE UP TO STANDARDS I AM HAPPY WITH **

playersonseason - The number of players on the season.


Possible Variables to include later:
timesreturned - times a player returned to the game.
daysplayed - number of total days the player played.
timesvotedout - Number of times a player was voted out during the season.

The 3 variables above were not included due to only compassing 6 seasons, being:
Pearl Islands, Redemption Island, South Pacific, Blood vs. Water, Edge of Extinction, Winners at War.

Most contestants would have a big fat 0 and 1 next to timesreturned and timesvotedout, because this dataset
doesn't account for return seasons.

daysplayed is still up for possible future consideration.


IMPORTANT NOTES:
Multiple Seasons - Final 3 voting
For any season with a final 2, only the person wins immunity and has to vote at the booth has it count as a vote they cast.
Likewise, instead of both players eligible to be voted having votesrecieved increased by 2 and 1, it just increases by 1 for the person voted out.
The SurvivorWiki also calculates votesrecieved under this assumption.
In cases like Palau where there was not a vote, nobody recieved any votes for or against.

Multiple Seasons - The Quitters
If a player quits at tribal council, everyone who attended that tribal council gets +1 to the tribalsattended variable, including the quitter.
IF a player quits at the beach, or anywhere except tribal, it is not considered a tribal council.
Same policy applies for medical evacuations.

Thailand - All Contestants
Before the merge, the option was given to the players to mutiny. However, no players ended up taking the option. Despite it technically being
a tribe swap, neither myself or SurvivorWiki recognize it as a swap, so timesswapped for all Thailand contestants is 0.

The Amazon - Heidi Strobel, Jenna Morasca
During the Final 6, Jenna Morasca won immunity, but didn't keep it, giving it to Heidi Strobel before the vote.
Under my personal judgement, I gave the immunity to Heidi, as she had it during the votes, having their indivual immunity count be 3,1 instead of 4,0 respectively.
This standard is kept for future occurences.

Pearl Island - All Contestants / The Outcasts
The outcasts returning to the game does not count as a tribe swap. Keep in mind that the outcasts essentially returned to the merged tribe, as the merged the night after they returned.
The voting for the outcasts who return also does not count to the voting stats.
Lillian Morris' and Burton Roberts' return immunities are not counted towards the stats. The immunity Burton won went to Rupert Boneham, so the immunity counts for Rupert.

Palau - Jonathan Libby / Wanda Shirk
Both were eliminated before tribes were sorted in Palau. Since Wanda Shirk was technically not selected for a tribe first, she gets the 20th spot, and Jonathan Libby gets the 19th spot.
Both of them get a starting tribe of No Tribe, and a starting tribe color of N/A. The same will apply later for Blood vs. Water.

Palau - Koror
Due to the Ulong tribe being decimated and absorbed, that will be treated as the merge.
There will be no tribe swap considered for the season, and all contestants left at the time of the absorption will have their merge tribe as Koror, regardless of starting tribe.

Cook Islands - Double Tribal
The double tribal where both Rebecca Borman and Jenny Guzon-Bee are both voted out subsequently is considered one tribal council.
The same treatment will be given to other "double tribals" in the future that have immunity challenges during them.

Fiji - Bula Bula
For the Final 10 vote, since the tribe was split into two groups, I count the win as a tribe immunity instead of an indiviual immunity.
This won't count as a tribe swap however.

One World - Monica Culpepper
Listed job as Homemaker, even if it might not be accurate to One World, as being refered to as the Ex-NFL Player's Wife is a bit degrading.
If you are really offended by this decision (for some reason), BvW connections override the returning player job.

One World - Salani & Manono Tribal Immunities
The immunity that Manono won and gave up will count as a Salani Immunity.
If you are reading this and ever go on, or go back on, DON'T DO THIS.

Caramoan - Brandon Hantz
Multiple circles have stated that the production team chose to eject Brandon before the impromptu challenge vote.
However, even if it was faux, a tribe (Gota) won immunity, and all 9 players on Bikal technically voted. The same will go
for future "Auto-Vote" occurences we saw in 45 and 46 for Hannah Rose and Bhanu Gopal respectively.

Blood Vs. Water - The Original Tribes
The way Day 1 was handled was really weird, as 2 contestants got auto-sent to Redemption Island, with their loved one being able to change places.
For the sake of simplicity, players sent to RI have no starting tribe, and everyone else starts on the original tribe.
The main impact is Laura Boneham starting on Galang, and all votes from this not counting towards stats.

Blood Vs. Water - John Cody & Laura Morrett
Due to not being in the game at the time of the season's tribe swap, rather being on RI, they are not swapped, and doesn't count towards their swap total.

Edge of Extinction / Winners at War - Final Placement
Placement of eliminated contests is first based on when they officially were eliminated or eliminated themselves from the game, followed by the order they
arrived on the edge.

Island of the Idols - Dan Spilo
He was ejected and pretty creepy. For the sake of correct data, it doesn't really reflect that, especially since he had 5 total votes against him at his ejection at Final 6.
While his stats stay the same, I just wanted to state that I don't condone the behavior, and wish I could rip him a new one in the file.

Winners at War
I decided to make a couple personal changes.
- Instead of returning player in the occupation tab as is normal for returning players, they are returning winners. This will be exclusive and not retroactively or given to future returning winners.
- Koru's tribe color is gold instead of black/yellow.

Winners at War - Jeremy Collins
Because of the use of the Safety w/o Power advantage at the Final 10 vote, it does not count as being at tribal due to the circumstances of him not voting.

New Era Seasons
If a player gets to the "Earn The Merge" stage and is voted out, they will still be counted as being a member of the merge tribe.
A "Earn The Merge" Team Win will count as a tribal immunity.

Survivor 44
The "Audio Slave" challenge on Episode 7, Frannie did all of the work.
For the case of split challenges, the contestants on the winning team who last the longest will get +1 individual immunity.

Survivor 45
Kendra McQuarrie observed Lulu for the afternoon after Lulu lost the first challenge, and then casted an anonymous vote.
This vote was for Brandon Donlon. However, given the quit, we did not know of the twist or vote.
For lack of immediate knowledge, this does not count as a casted vote for Kendra, or a vote against Brandon.

Survivor 47
Since the Earn The Merge is for individual immunity again, only the overall challenge winner, Kyle Ostwald, gets an immunity win.
