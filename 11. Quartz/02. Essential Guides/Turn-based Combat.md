---
Topic: Turn-based Gameplay
tags:
  - HSR
  - "#SpeedAV"
  - SpeedAV
aliases:
  - Speed
  - Breakpoint
  - AV
  - AV Advance
  - Action Value
cssclasses:
  - center-titles
  - no-embed-border
  - image-borders
  - wide-page
  - center-images
share: "true"
Links: "false"
Last_Updated: 2024-11-06
---
>[!context] **This guide is separated into 2 sections.**
>The 1st Section contains explanations a short explanation on characters' Base Stats and explanations on common terms which are good to know, even if you don't plan on doing things like clearing Memory of Chaos in the 1st cycle (0c).
>
>The 2nd Section contains an explanation on SPD Break Points, examples and how to check what SPD your characters ***actually*** have.

## Character's Base Stats
Characters' Base Stats, including Base SPD, are found by clicking the "More Stats" button when checking a character's details. The Base Stats are in gray.
![[../Media/Robin Stats Example.png|260]]
![[../Media/Robin Stats Example 2.png|400]]
They can also be seen in-battle:
![[../Media/Screenshot_1222.png|400]]
## Common Terms
Nomenclature and their explanations.

If it helps you, you can think of these first 3 terms like you do in physics. 
### Action Gauge = Distance needed to be travelled.
**By default, characters will have to traverse 10000 Action Gauge before they can have their turn.**
- Action Gauge can *not* go into the negatives.

### Speed = Speed at which a character travels the Distance.
- The SPD Stat characters have can have additional decimals. Check your characters’ SPD stats with 3 decimals at https://enka.network by hovering your cursor over the SPD stat shown there.
>[!warning] If you have a character's SPD being buffed by a percentage, the buff will not be equal to the character's SPD before the buff, but to that of their **Base** SPD.

### Action Value = Time spent travelling the Distance.
- This is the metric that actually matters in Honkai: Star Rail, as end-game content tracks your performance based on either:
  - The Cycles you take in Memory of Chaos. More details on cycles is found below.
  - The amount of AV you take to kill the boss in Apocalyptic Shadow.
  - How many enemies you've killed in Pure Fiction.

### Cycles
A Cycle is a unit of measurement, used by the game to gauge performance.
- The first cycle at the start of battle in Memory of Chaos and Pure Fiction contains 150 AV.
- Switching waves in Memory of Chaos also resets the current cycle's action value and makes its max 150 again. This does **NOT** happen in Pure Fiction.
- Other cycles contain the normal 100 AV.

### Action Forward
Action Forward reduces the Action Gauge that needs to be travelled by a percentage of the base Action Gauge (10000). 
For example, 25% Action Forward → -2500 Action Gauge.
- Action Forward is **NOT** *always* the same as ”Immediately Taking Turn”. Look below for an explanation.
- If Action Forward exceeds remaining Action Gauge example , it will __not__ go into the negatives and will instead allow you to instantly act, like in the example below:
Remaining Action Gauge = 2365, Action Forward = 25% → `Action Gauge after 25% AF = 0` → Character will Immediately Act

>[!tip] A character doesn’t always need to get Advanced Forward right after their turn for them to make full use of the action forward.
  As long as action gauge remaining until your turn is equal to or higher than the amount reduced by the action forward, you will make full use of the Action Forward amount.

### Action Delay
Action Delay works in the exact same way as Action Forward, with the exception of it being a debuff instead of a buff; increasing the Action Gauge that the unit needs to travel.
Example: 40% Action Delay → 4000 extra Action Gauge needed to be travelled.

### Immediate Action
Immediate Action is the ability to immediately have another ally or yourself act, ignoring remaining Action Gauge and Action Value.

>[!warning] *100% Action Forward **≠** ”Immediately Take Action”*

If the advanced forward ally has more than 10000 Action Gauge remaining (got their action delayed), then they won't take their turn 0 AV after the Action Forward. Whereas abilities that say ”immediately take action” always set Action Value to next turn to **0**.

List of abilities that make allies immediately take action:
- Robin’s Ultimate
- Bronya’s Skill
- March 7th Hunt’s Talent
- Dan Heng’s Eidolon 4
- Sushang’s Ultimate
- Gepard’s Eidolon 6.

### Extra Turn
Extra Turns means turns that are taken outside of a unit’s normal turn order, that don’t tick down buffs and debuffs' turn duration.
- Seele’s Talent ”Resurgence”, Firefly’s Eidolon 2, Qingque’s skill, Blade’s Skill and Boothill’s skill all count as an extra turn.

- All Ultimate abilities are considered extra turns.
- *Extra turns have a lower priority than Follow-up Actions of any kind.*
- If multiple Extra Turns and Ultimate Abilities are queued, they will be performed in the order they are triggered, with the exception of Blade’s, Qingque’s and Boothill’s skills that are pushed back by Ultimates.

### Follow - Up Actions
Follow Up Actions are actions that are generally automatically triggered and ignore turn order. They don’t retain buffs active during the turn they are activated. For example, Ratio’s skill Follow-Up Attack.
- Follow-Up actions triggered upon entering a battle take place after the Toughness Reduction of an over-world attack or Technique (as well as Simulated Universe 99% HP enemy hp reduction.)
- **Counters** are Follow-up Attacks initiated after the character gets hit. Characters that can initiate counters = Clara, Yunli and March 7th Preservation.
- Natasha’s Eidolon 1 is a rare example of a Follow-Up Action done without a Follow-up Attack and without an appearance on the action order.

## Calculating AV
Please keep in mind the points from the previous section when reading and trying to understand this section's content.

As said before, AV is the metric that is being tracked and what we will work with.
It's also possible to instead calculate the amount of SPD a character needs, which we will be getting into shortly.

You find the amount of AV taken by a character until they can have their turn by dividing the Action Gauge by the SPD the character has while travelling that Action Gauge.
This is the formula.
$${Action {\space} Gauge \over Character {\space} SPD} = AV {\space} Taken$$
You can of course flip it around if you want to find different things.
$${Action {\space} Gauge \over AV} = Required {\space} SPD$$
$${AV \times SPD} = Action {\space} Gauge$$
For a normal turn, Action Gauge will always be 10000.
With that in mind, if you want to calculate for multiple turns acting at the same speed, then you would do the following, with N being the number of turns:
$${10000{\space \times} \space N \over AV} = Required {\space} SPD$$
A practical use for this would be finding out the required SPD for a character to have 2 turns within the first Cycle at the start of battle, calculated as below:
$${10000{\space \times} \space 2 \over 150} = 133.3333... {\space} SPD$$
>[!tip] Since we can only see up to 3 decimals for our characters' SPD, it's common practice to round up to the 3rd decimal.
>So instead of a 133.333 SPD Requirement, it's 133.334.


Now, if you want to take into account Action Forward or Delay, then your formula will change into:
$${Action{\space}Gauge{\space}-(10000\space\times Action\space Forward/Delay)\over Character{\space} SPD} = AV {\space} Taken$$

If you also want to take into account buffs/debuffs to a character's SPD, then it will depend on **after how much AV** the SPD buff was applied.
- If the SPD Buff is applied right after or during a turn, before travelling any Distance or AV.
In this case, you will simply just add the buff to the character's SPD.
$${Action{\space}Gauge-(10000\times Action\space Forward/Delay)\over Character{\space} SPD +/- SPD} = AV {\space} Taken$$
- If the SPD Buff is applied anytime during a character's travel to their next turn, then the calculation will be a bit different. Check the below section for more details.

### Mid-Travel SPD Changes
Calculating for this type of problem is more complicated, as it will have to depend on *exactly* when the speed change is applied. As implied by the word "Change", it doesn't necessarily have to be a buff; it can also be the loss of a buff or the application of a debuff on the character.

What you will want to do is first figure out when the speed buff is applied exactly, at what AV.
- For something like Jade or March 7th Hunt, it's when they can have their first turn as the SPD Buff is given by their Skill.
- For something like Firefly or Robin with her E2, it's when their Ultimate expires that they or their allies lose the SPD Buff.

After finding out when exactly the SPD Change is applied, what you'll want to think about is how many turns you want on a character before and after the SPD Change, and within how much AV.

#### Example: March 7th's Skill
Once it is used on a target ally, their SPD is increased by 10% (10.8% at Skill LVL 12) of their base.
This also means that the speed buff will not be applied until March travels to her first turn at the start of battle, making the SPD Buff less impactful for break points like 133.334 and 200 for the first wave in Memory of Chaos.

The crucial point for this calculation is simply the fact that the first turn of the character you designate as March's Master will be split up into two parts: before and after receiving the buff.

Calculations will have to depend on the SPD March 7th's has, as it affects the time when the buff is applied unto the target ally.
It's usually best to equip March with SPD main stat boots, but to not look for SPD sub-stats further than that as long as March 7th ends up being faster than the character you designate as her Master.
Because of this, we'll just be using the SPD March 7th Hunt has using SPD main stat boots and without any SPD sub-stats, which is 127 SPD.

We'll use Feixiao as the example character that we want to get buffed by March 7th, so that she can gain the effects of the 133.334 SPD Break Point (2 Turns within the 1st Cycle) **for the first wave**.
- Feixiao's Base SPD is 112, so the amount of SPD she'll gain from March 7th with a LVL 10 Skill is 11.2. We're considering March 7th Skill is LVL 10 for the sake of simplicity.
- March 7th has a Ascension-locked Ability Trace that advances forward her action at the start of battle by 25%. This is important to keep in mind for the calculation as it helps her apply the buff quicker.
- We want Feixiao to get 2 Turns within the 1st Cycle, specifically in the first wave, which means we won't have the luxury of assuming that the skill lingers from the previous Wave.
  
Considering the above, the steps you will want to take to find the answer are as follows:
1. We'll need our equation to equal 150, as it's the amount of AV contained within the first wave at the start of battle and after switching waves in Memory of Chaos.
2. Calculate the AV taken for March 7th's first turn. This Action Value passes not only for March 7th, but for Feixiao too.$$150={7500\over 127}$$
3. Calculate the AV taken for one of Feixiao's turns without the speed buff.$$150={7500\over 127}+{10000\over x}$$
4. Subtract from Step 3's part of the calculation, the AV taken for March 7th's first turn at the start of battle with her 25% Action Forward.$$150={7500\over 127}+{10000\over x}-{7500\over127}$$This step, together with the previous step, calculates the amount of Action Value Feixiao still needs to take until she can get to her first turn.
   The following 2 steps, together with the step 2 and 3, calculate us the amount of Action Value will actually have to travel for, after she is buffed by March 7th.
   
5. Multiply the result of the subtraction between step 2 and 3 by Feixiao's SPD.$$150={7500\over 127}+({10000\over x}-{7500\over127})\times x$$
6. Divide the result of Step 5 by Feixiao's new SPD, after it gets buffed by March 7th.$$150={7500\over 127}+{({10000\over x}-{7500\over127})\times x\space÷\space(x+11.2)}$$
7. ***Final Step*** Finally, after finding out the total AV taken by Feixiao before and after March's SPD buff, all we need to do is to calculate Feixiao's 2nd turn AV and add it in.
$$150={7500\over 127}+{({10000\over x}-{7500\over127})\times x\space÷\space(x+11.2)}+{10000\over x+11.2}$$

#### Example: Firefly's Ultimate
which lasts until the Countdown acts with a SPD of 70, her SPD change will happen at 10000 ÷ 70 = 142.8571428571429... AV. It will be 60 flat SPD loss.

For the same example, let's say we wanted to calculate how much SPD Firefly would need out-side of battle, such that she is able to get 2 turns within her Ultimate and a 3rd turn outside of the Ultimate before the first cycle ends; **in the second wave**.
We will also be assuming that Firefly's Ultimate was active at the time the 1st Wave was cleared, making it linger over into the 2nd Wave with its duration **reset**.

Using Firefly's usual teammates, those being Ruan Mei, Harmony MC and Fugue / Lingsha / Gallagher, Firefly's SPD will be permanently buffed by 10% of her base by Ruan Mei.
Firefly's Base SPD stat is 104, meaning Ruan Mei will increase Firefly's speed by exactly 10.4

Considering the above, the steps you will want to take to find the answer are as follows:
1. We want to find Firefly's Required SPD for acting **within the first cycle after changing waves**.
   This means that we'll need our equation to equal 150, as it's the amount of AV contained within the first wave at the start of battle and after switching waves in Memory of Chaos.
   
2. Calculate for all 3 of Firefly's Turns' AV as if they were all performed with her Ultimate's SPD Buff active. x = Firefly's SPD outside of battle$$150={3\times 10000\over x+70.4}$$
3. Subtract from the result, the amount of AV Firefly's Ultimate lasts for.$$150={30000\over x+70.4}-{10000\over70}$$We do this to find the Remaining AV that still needs to be travelled after the Ultimate ends.
   This helps us for the next part of the calculation, takes into account the AV taken between the 2nd Turn's end and the Ultimate's end and effectively removing the need to calculate it.
   
4. Take the result from step 2 and multiply it by the SPD Firefly has during her Ultimate.$$150=({30000\over x+70.4}-{10000\over70})\times (x+70.4)$$By doing this, we turn the left-over Action Value into Action Gauge.
   Turning AV into AG helps us with the next step of the calculation, which is to find out the AV taken by Firefly to travel to her 3rd Turn without her Ultimate's SPD Buff.
   
5. Take the result from step 3 and divide it by the SPD Firefly has out-side of her Ultimate. $$150={({30000\over x+70.4}-{10000\over70})\times (x+70.4)\over x+10.4}$$As said in the previous step's explanation, we are performing this to find Firefly's AV taken for the 4th turn out-side of her ultimate **according to Firefly's "x" SPD** that we ultimately want to find.
   After this, the only thing left to do is add to the result the amount of AV Firefly's Ultimate lasts for.

6. ***Final Step*** Take the result from step 5 and add the AV duration of Firefly's Ultimate.$$150={({30000\over x+70.4}-{10000\over70})\times (x+70.4)\over x+10.4}+{10000\over 70}$$This is the final version of the calculation. If you've understood the steps thus far then you understand how the calculation works and how we've come to it. 
   
If you want to lower the SPD Requirement further, by having Harmony MC use DDD, then you can just decrease the amount of Action Gauge travelled by Firefly in total. So for the above example, if you have 1 proc of S5 DDD then you would put 27600 instead of 30000.
It also doesn't matter when you use Dance! Dance! Dance!, as its value will stay the same, whether you use it during Firefly's ultimate or after it ends, as long as the proc is sometime within the AV you're aiming for.



## SPD Break Points 
Break points are specific amounts of SPD required for a character to have a certain amount of turns, within a certain amount of cycles.

#### Thresholds:
Assuming you have no sources of Action Forward present.
The SPD Stat characters have can have additional decimals. Check your characters’ SPD stats with 3 decimals at https://enka.network by hovering your cursor over the SPD stat shown there.

| Required SPD  | Turns over 6 Cycles | Turns over 2 Cycles | Turns in 0 Cycle |  Value/Worth  |
| :-----------: | :-----------------: | :-----------------: | :--------------: | :-----------: |
|    92.308     |          6          |          2          |        1         |      low      |
|    107.693    |          7          |          2          |        1         |      low      |
|    123.077    |          8          |          3          |        1         |      low      |
|   $133.334$   |          8          |          3          |   ==***2***==    |   **high**    |
|    138.462    |          9          |          3          |        2         |      low      |
|    153.847    |         10          |          3          |        2         |      low      |
|   $160.000$   |         10          |          4          |        2         |   **high**    |
|    169.231    |         11          |          4          |        2         |      low      |
|    184.616    |         12          |          4          |        2         |      low      |
| **$200.000$** |      ***13***       |       ***5***       |   ==***3***==    | **very high** |
|    266.667    |         N/A         |         N/A         |      **4**       |     high      |
### Tables: 
![[../Media/Speed-Chart 2.png|../Media/Speed-Chart 2.png]]
Credit to Mr. Pokke.

![[../Media/Speed-Chart1.png|../Media/Speed-Chart1.png]]
### Relevant Breakpoints with Action Forward
**Effective 200 Speed (3 Turns in cycle 0)**
Using Dance! Dance! Dance! light cone
- S5 DDD = 184.000
- S4 DDD = 185.334
- S3 DDD = 186.667
- S2 DDD = 188.000
- S1 DDD = 189.334

Using 4-Pc Eagle of Twilight Line set effect = 183.334

Using DDD and 4-Pc Eagle of Twilight Line
- S5 DDD + Eagle = 167.334
- S4 DDD + Eagle = 168.600
- S3 DDD + Eagle = 170.000
- S2 DDD + Eagle = 171.300
- S1 DDD + Eagle  = 172.600

**WAVE 1 ONLY Effective 200 Speed**
Dance! Dance! Dance! + 2-Pc Sprightly Vonwacq
- S5 DDD + Vonwacq = 157.300
- S4 DDD + Vonwacq = 158.600
- S3 DDD + Vonwacq = 160.000
- S2 DDD + Vonwacq = 161.300
- S1 DDD + Vonwacq  = 162.600

Dance! Dance! Dance! + 4-Pc Eagle + 2-Pc Vonwacq
- S5 DDD + Vonwacq + Eagle = 140.600
- S4 DDD + Vonwacq + Eagle = 142.000
- S3 DDD + Vonwacq + Eagle = 143.300
- S2 DDD + Vonwacq + Eagle = 144.600
- S1 DDD + Vonwacq + Eagle = 146.000

4-Pc Eagle + Vonwacq = 156.600

**Effective 160 (4 Turns in first 2 cycles)**
- 4-Pc Eagle = 150.000

- S5 DDD = 150.400
- S4 DDD = 151.200
- S3 DDD = 152.000
- S2 DDD = 152.800
- S1 DDD = 153.600
  
We hope you found this guide helpful.
You can check out more guides, information and game data On our home page [[../index|here]]. 