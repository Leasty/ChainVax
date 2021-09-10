# ChainVax


## Analyse Covid_Infeciton Rate ##

---

<img src="./readme_images/covid_spread5x.gif" alt="covid_spread" width="50%"/>

COVID19 data was collected from https://data.nsw.gov.au/nsw-covid-19-data.

Cleaned up data to remove null values and 'Masked' data.

Using pgeocode, iterate through the data frame index and collect longitutde and latitude values from the postcodes.

Prepare data frame by setting the date as the index, adding a count column and dropping unused columns.

Plot the data on a mapping of NSW using the longitutde and latitude data to show which areas are most affected by COIVD19.
![covid_map](./readme_images/covid_map_interact.gif)

---

## Solidity ##

To finalise our ChainVax process onto the blockchain, we incorporated a Solidity Contract using the Remix IDE.

The ChainVax contract runs on version 0.5.5 and inherits from the ERC721Full and Counters contract. 
There is a struct for variables we require from the patient followed by a registerVaccination function. 
The function contains a few uses such as token id increasing by 1 every time a new person gets vaccinated, minting the non-fungible token with the variable input and transferring that NFT to the wallet address of the person who got vaccinated.
The team chose to keep it simple with only one function encompassing the entire use cases mentioned above to minimise interaction between the Python script and Solidity to reduce potential mistakes. 
When the contract is deployed, there are a few settings to be updated in the python script before the ChainVax blockchain can be utilised. 
Firstly, the ABI will have to be updated in the JSON file. 
Next, the newly deployed contract address also needs to be changed in the top of our python script variables. 
Finally, please ensure that the operator address for the entire ChainVax procedure remains constant as the ChainVax contract requires the owner’s address to operate.
Besides the registerVaccination function mentioned, the other function heavily used is called totalSupply and these two remain the most important function for our project. 
The totalSupply function is vital to ensuring our minting records are updated properly as we are using the python script to extract the token id information from the ChainVax contract using the totalSupply function which contains the total index length of tokens in the contract that has been minted.