# Hyperverse-FastCamp
###Decentology Assignment 1

Utilizing the [Hyperverse](https://www.hyperverse.dev/) is a way to build an open minting site without writing smart contract codes. It is an open marketplace of smart modules that allows Javascript developers to build web3 apps. There are many smart modules  that smart contracts developers built which is provided to the community to use. These are verified after auditors stake their tokens, which can be seen like a vote of confidence. Compared to the web2 world, we can treat the Hyperverse like calling the Google Maps API instead of building out a map feature on a website. 

A good resource is [docs.hyperverse.dev](http://docs.hyperverse.dev) for more information and details. Before we begin the first step of building an open minting site, we have to make sure we have our local environment set up. The easiest way is to clone the Hyperverse monorepo. This provides all the project source code we need to start building our own application. There are a couple modules available depending on what blockchain you want to build on. For the purpose of this site, we are navigating to ethereum and picking ‘ERC721’ to build out a NFT minting page. 

Once that is set up, we can open [localhost:3000](http://localhost:3000) to see the ERC721 smart module. We first need to connect our Metamask account and make sure we have testEth avaliable in our wallet. That can be funded through [faucets.chain.link](http://faucets.chain.link). After that is done, we want to create our own instance of an ERC721. This is done in order to create our own contract with our own data. We need to come up with a token name and a token symbol. Then we confirm this on our wallet. To verify everything is happening correctly is to go on [rinkeby.etherscan.io](http://rinkeby.etherscan.io) and see the contract being created in real time. Next, we click on the “Get Proxy Token” in order to get our proxy contract address. Now once this is created, we can create an NFT for other users to mint. We first have to make sure our tenant ID is updated. The tenant ID is pointing to the wallet address that created the instance which is where it is pulling data from and where it’s looking back to when calling other functions. So, it’s a very important step that needs to be done after every instance is created. Now we can click the mint button under “tenant owner functions”. We have to insert a wallet that we want to send the NFT to and an image attached to the NFT. A way to test this is to send it to ourselves. After paying the gas fees and steps that pops up on the wallet, we can go back to [https://rinkeby.etherscan.io/](https://rinkeby.etherscan.io/) and see all of the transactions that occurred. We can verify that the NFT was successfully transferred by clicking the Balance Of button and inserting the wallet address the NFT was sent to. 

Within the actual code, we are looking at the code within /etherum/ERC721/pages/_app.tsx, specifically within the MyApp function where we can see what modules we are using. This is where we can add several different Hyperverse modules depending on what functionalities we want. When we are building out the site, we want to start under components/writeFunctions/Nav.tsx. This contains everything we need to have the connect component which allows us to connect a wallet. Next file we need to look at is the Container.tsx file which contains the javascript code we need for each of the individual functionalites. For creating a new instance, we are looking at CreateInstance, and after we pass in the appropriate fields needed, these functions will run for us. These are the basic steps and knowledge needed to build out our own open minting site using the Hyperverse.
