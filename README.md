# Urban Farm 4.0
Projects to inject Digital Twin analysis into Farming

## [Bees] Guardian at the Gate  
Varroa Mites (a parasite that invests larval chambers in a hive, killing the nascent bee and contributing to Colony Collapse) rest on potential flowers and hitch a ride on pollen-gathering bees, and are carried back to the bee's home hive.  AI and IoT systems can be integrated into a variation of a [Pollen Catcher](https://happbeeacres.com/product/pollen-trap/) to screen incomming bees for infestation.  Bees carrying mites (and other potential dangers, like invading wasps)can be removed from the population, but they need to be identified first.  

--> [Dataset](https://www.tensorflow.org/datasets/catalog/bee_dataset)  
The pictures were of bees in a number of states.  They were all shot on the same green background for contrast.

Bees actively cooling the hive (wings becoming too fast to process with the camera) →  
![Example-1_0_0_0 - Cooling](https://github.com/user-attachments/assets/8c2f5116-2d23-4e86-ac62-c86d1021427b)  
  
Bees with their pollen sacks full →  
![Example-0_1_0_0 - Pollen](https://github.com/user-attachments/assets/462375ea-b976-4219-b953-be1cc66dbd32)  
Note - This was included to help prevent false positives later.

Bees with Varroa mite contamination →  
![Example-0_0_1_0 - Verroa](https://github.com/user-attachments/assets/1951b34c-4714-4fa1-9b82-94b4fa3ddfe7)  
  
And "non-bees", or in this instance, wasps →  
![Example-0_0_0_1 - Wasp](https://github.com/user-attachments/assets/8487b0e0-8b7f-462a-aff7-e8e198b06a3b)

Adding to the overall complexity, some pictures had bees in multiple states, such as a Varroa-infected bee cooling the hive →  
![Example-1_0_1_0 - Cooling and Verroa](https://github.com/user-attachments/assets/556fdd85-1058-425d-94e1-f0b5a9391f84)  
Because of this, all the individual states would have to be processed separately.

The dataset was too large to process all the pictures(colab, 16Gb +), so the training operations were broken into optimized chunks (Colab, 3Gb). This would allow the system to only pull the files needed for the present training cycle, and removed the upper *system* limit for training and testing pictures (5,992 and 1,498, respectively). With this modification in place, I was able to run several training models in parallel.
  
The model was branched to give a separate binary output for each of the possible states...  
![Bee_pic - Model](https://github.com/user-attachments/assets/315ed61c-6156-4995-82b8-a5105a1a3254)  
... and Varroa Mite detection was optimized to ~95.5% accuracy.  The model was optimized several times and this seems to be the limit of the present training data, with 10 epochs being the limit before over-fitting occurred.  
![Bee_pic - Accuracy - e10](https://github.com/user-attachments/assets/c017f03d-cf90-454a-8b60-6237501d5340)  
![Bee_pic - Accuracy Graph - e10](https://github.com/user-attachments/assets/ad295e2a-09d5-4a20-b532-d970154fcbf8)  


Future state -
- X/Y coordinate
- Individual bee identification
- Incoming trajectory tracking
- Maximum ZOT
- Minimum ZOT
- Air Popper design (field maintenance)


## [Bees] Heat Matters  
--> [Link](https://cordis.europa.eu/article/id/443713-a-robotic-system-to-save-the-bees#:~:text=%E2%80%9CThe%20thermal%20sensors%20create%20a,the%20use%20of%20intrusive%20cameras.%20%E2%80%9C)  
Initial Step - Fact Finding.
- [Observation Hive](https://www.sustainability-times.com/sustainable-business/scientists-in-europe-are-arming-queen-bees-with-robots-and-smart-hives-to-save-their-colonies/#:~:text=This%20could%20have%20another%20virtuous,Read%20the%20original%20article.)  
- Observation Hive - "Shattered" design and maximum offset length (→ Holland)
- [Defense](https://scientificbeekeeping.com/a-test-of-thermal-treatment-for-varroa-part-1/)
- Cell Placement
- Cell Routing safety
- EM limits
- Placement application for displaced thermal differential

## [Fish] Fish Food  
--> [Dataset](https://data.cnra.ca.gov/dataset/inland-fisheries-length-weight-ds195)  
Initial step complete - Logistic Regression model constructed to determine weight ƒ(Length)
- This is for proof of concept.
- See Weight Tank.  
![Fish Pic - Weight as a function of length - Rainbow Trout](https://github.com/user-attachments/assets/bbf5432c-faf9-4c5b-9184-62311e0e47ce)  

## [Fish] Fish-al Recognition  
--> [link](https://www.nature.com/articles/s41598-021-96476-4)  
Initial Step - Hardware Set up [Open CV] (Project - Post 10/21/24)
Next Step - Initial meeting with supervisor complete (RN - 11/08/24)  
Future state -
- 2nd Supervisor ??? (DC)
- [Calcein](https://en.wikipedia.org/wiki/Calcein) ([Source](https://www.thermofisher.com/order/catalog/product/C3099))
- Contact [Hatchery](https://nwifc.org/fish-marking-a-better-way-to-dye/)
- Data acquisition loop ("Home" cell)
- buy goldfish

## [Fish] Weight Tank  
Initial step complete - Half-shell Tank designed (PTC Creo)  
Next Step - Design list  
Future state -  
- Complete Density Check
- Complete Supervisor Check
- Complete Window Check
- Verify load strain mitigation (controlled loop)
- Construct
- Build incident alarm (or shift to limited feedings)

## [Fish] Breath of the Water  
When all else is done, we begin.

## [Fish] Invisible Hand
All good things come to an end. 

## [Watermelon] Sweet Sound of Victory 
--> [Dataset](https://ieee-dataport.org/documents/watermelon-appearance-and-knock-correlate-data-sets-sugar-content)  
Dataset Identified.

## [Aux] Lend a Hand  
Project on hold (10/21/24)


## [Aux] Go for a Stroll  
Initial step complete - Chassis assembled  
Next Step - DC drive motor controller on order  
Project on hold (10/21/24) 
