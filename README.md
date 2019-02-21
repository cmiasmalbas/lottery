# Hyperledger - Lottery Game with Design Process <br>

## Simple Lottery
The simple lottery will be nonrecurring, uses blockhashes for random numbers, and has only one winner. <br>

**Design Process:** <br>
![alt text](https://github.com/cmiasmalbas/lottery/blob/master/SimpleLottery.png)

**Instruction:**
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
## Recurring Lottery
This lottery will occur in rounds so that a new prize pool is started every time the old one closes. It will also allow users to purchase multiple tickets in one transaction instead of just one and add a couple of security improvements. <br>

**Design Process:** <br>
![alt text](https://github.com/cmiasmalbas/lottery/blob/master/RecurringLottery.png)

**Instruction:**
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

## RNG Lottery
This lottery game is or a one time random number. It will be instituting time delays between the ticket purchase period and the drawing of the winner, so that the blockhash used to determine the winner is not known at any point when lottery tickets are being distributed.. <br>

**Design Process:** <br>
![alt text](https://github.com/cmiasmalbas/lottery/blob/master/RNGLottery.png)

**Instruction:**
+ Open the browser and go to remix.ethereum.org 
+ Copy the contract from SimpleLottery.sol in the remix
+ The admin will initiate the contract
+ Click the Run tab
+ The participant submits commitment hash when buying a tickets
+ CreateCommit function is for the hashing the address with the corresponding the guess number. One number only. Input value for CreateCommit is: "(address)", (guess number).
+ The user will choose what number they want to submit
+ When user submitted their number, system will save the secret number and address to ticketlist in world state
+ When ticketing period is over, user cannot purchased any tickets.
+ When ticketing period is over, All user must reveal their secret number to know who is the winner
+ After revealing, the system will verify whose secret number was the winner
+ If the users failed to submit their numbers and addresses they will drop to Lottery.
+ System will draw the winner and verify if the number is existing.
+ Generate random number, it will enable to select the user’s address to ticketlist. -Generate random seed for picking a winner, this is random seed to determine the winner. Each time a secret number is revealed, the seed is modified to incorporate the reveal.
+ Balance will be added to user’s address and will added to world state to verify the address of the user.

