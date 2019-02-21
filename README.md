# Hyperledger - Lottery Game with Design Process <br>

## Simple Lottery
The simple lottery will be nonrecurring, uses blockhashes for random numbers, and has only one winner. <br>

**Design Process:** <br>
![alt text](https://github.com/cmiasmalbas/lottery/blob/master/SimpleLottery.png)

+ Open the browser and go to remix.ethereum.org 
+ Copy the contract from SimpleLottery.sol in the remix
+ The admin will initiate the contract
+ Click the Run tab
+ The admin should set the lottery duration and save to world state the total duration
+ For testing, put 60 (seconds) and click the create tab for the lottery duration
+ The participant will buy a ticket by putting a 1 value in ether 
+ You can buy tickets as long the duration is not end. It will prompt an error if the duration is ended. You can also change the address upon buying ticket.
+ When the participant successfully bought a ticket, System add user's addresss to ticket list in world state
+ When duration will lapsed, the admin will draw the winner if he/she will be the winner.
+ Click draw winner button. It is for choosing who's the winner.
+ Viewing the winner wil be the winner button. It will give a address of the winner.
+ When user draw the winner, the system will generate random unsigned integer
+ After that, system will Use the generated integer to select an adress to Ticket list in world state
+ After that, system will Assign winner's address that will retrieved in world state
+ When the address verified successfully, the user will withdraw the prize.
+ When withdrawing the prize the system will transfer balance to winner's address
+ Click claim for the claiming the prize.
<br> 
<br>
## Recurring Lottery
This lottery will occur in rounds so that a new prize pool is started every time the old one closes. It will also allow users to purchase multiple tickets in one transaction instead of just one and add a couple of security improvements. <br>

**Design Process:** <br>
![alt text](https://github.com/cmiasmalbas/lottery/blob/master/RecurringLottery.png)

+ Open the browser and go to remix.ethereum.org 
+ Copy the contract from SimpleLottery.sol in the remix
+ The admin will initiate the contract
+ Click the Run tab
+ The admin should set the lottery duration and save to world state the total duration
+ The participant can buy ticket
+ The admin will end the time or duration lapsed
+ The admin will draw the winner
+ When admin draw the winner, the system will generate random unsigned integer
+ After that, system will Use the generated integer to select an adress to Ticket list in world state
+ After that, system will Assign winner's address that will retrieved in world state
+ When the address verified successfully, the user will withdraw the prize.
+ When withdrawing the prize the system will transfer balance to winner's address
+ Add 1 to round counts
+ The system will initiate new rounds
+ If the round counts is less than or equal to 100, the system will be deleted 1 round
