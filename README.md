<a href="https://webcomicname.com/" target="_blank">![Webcomic Name](images/oh-no.png)</a>
_Webcomic made by [Alex Norris](https://webcomicname.com/about) ([Website](https://webcomicname.com/), [Twitter](https://twitter.com/dorrismccomics), [Facebook](https://www.facebook.com/webcomicname/), [Instagram](https://www.instagram.com/webcomic_name/)) - Support him on [Patreon!](https://www.patreon.com/alexnorris)_

# PennySeed
_Decentralized Income ([Demo](https://twitter.com/ConcreteSciFi/status/1174141943070085124))_

## 📚 Table of Contents
[💰 Monetization Today](#-monetization-today)  
[😔 Problems](#-problems)  
[💡 Insight](#-insight)  
[🤩 Solution](#-solution)  
[🔧 Implementation](#-implementation)  
[📱 User Experience](#-user-experience)  
[👩‍💻 Developer Experience](#-developer-experience)  
[👍 Benefits](#-benefits)  
[🤔 Use Cases](#-use-cases)  
[📈 Revenue Model](#-revenue-model)  
[🌎 Building a Community](#-building-a-community)  

## 💰 Monetization Today
1. Pay-per-Media  
✔️ Money comes from Users  
❌ Hard to Share and reach more people  
❌ Price is arbitrary due to no overhead  
❌ Worry about Piracy and Torrenting  

2. Subscription  
✔️ Users pay a regular fixed amount  
✔️ Users can access all content  
❌ Users still pay even if no new content is created  
❌ Users have to subscribe for a period just to watch a single piece of content, cancelling after  

3. Streaming  
✔️ Users pay a regular fixed amount  
✔️ User payment is distributed amongst creators based on streamed content  
❌ [Pay-per-Stream](http://www.streamingroyaltycalculator.com/) model can be [exploited](https://www.rollingstone.com/music/music-features/fake-streams-indie-labels-spotify-tidal-846641/)  
❌ Rewards replayability over quality  
❌ Incentivizes Creators to exploit fans to stream their content multiple times for [cheap prizes](https://get.renaissance.app/)  
❌ Users have to subscribe to an entire Network even when they just wanna watch 1 or 2 creators' content  

4. Advertising  
✔️ Content can be free  
✔️ Can Share and reach more people  
❌ Incentivizes Creators to generate clickbait content  
❌ Money comes from sponsors, not viewers  
❌ [Creators are beholden to sponsors](https://youtube.fandom.com/wiki/YouTube_Adpocalypse), compromising content  

5. Donations  
✔️ Money comes from Users  
✔️ Content can be Free  
✔️ Quality over Quantity, since more content doesn't mean more donations  
❌ Users aren't sure how much to pay (nor how much the Creator needs/has)  
❌ Unstable income due to irregular donations  
❌ Users can be emotionally manipulated into donating  

6. Crowdfunding  
✔️ Money comes from Users  
✔️ There's a clear goal for users to reach  
✔️ Content can be Free  
❌ Once passed the goal, anything extra could've gone to other Creators they supported  
❌ Winner-takes-all approach where few popular Creators get the bulk of the potential pledges  
❌ Irregular pledge amounts lead to pandering to large pledgers who contribute most of the funding  

7. Merchandise  
✔️ Money comes from Users  
✔️ Free advertising from wearers  
❌ Users who want to support the Creator may not want that particular product  
❌ Creators are incentivized to sell cheap products for high prices for greater profits  
❌ Manufacturing & Shipping Fees  

## 😔 Problems
❌ [Processing Fees](https://stripe.com/pricing) (e.g. [Stripe](https://stripe.com/) charges 2.9% + $0.30 per payment)  
❌ Arbitrary Pricing with no guarantee of a stable income  
❌ Not extendable for custom incentive structures  

## 💡 Insight
- The Creator wants everyone to enjoy it
- Most of the money goes to living expenses
- Fans aren't paying for Content - they're paying for Future Content

## 🤩 Solution
✔️ A "Split-the-Bill" Model that divides the Target Amount by the number of Pledgers  
✔️ A Minimal Design that doesn't try to be a Social Network  
✔️ An Extendable Architecture that allows for integration with existing Content Production, Distribution, and Discovery Applications  

## 🔧 Implementation
⚙️ Ethereum via [Solidity](https://solidity.readthedocs.io/en/v0.5.10/) for [minimal processing fees](https://bitinfocharts.com/comparison/ethereum-transactionfees.html)  
⚙️ Blockchain ledger via [Web3](https://web3js.readthedocs.io/en/1.0/) for Proof-of-Pledge  
⚙️ [Stripe](https://stripe.com/docs) fallback for conventional payment methods, with the [processing fees](https://stripe.com/pricing) (2.9% + $0.30 per pledge) pushed on the pledger's end to incentivize adoption of a crypto-wallet like [MetaMask](https://metamask.io/)  

## 📱 User Experience
1. A Creator creates a Campaign, specifying the following:
    - Campaign Description
    - Target Amount
    - Minimum number of Pledgers or Maximum Amount per Pledge
    - Deadline
2. A page is created, including the Campaign Details, the current number of Pledgers so far, and a "Pledge" button
3. The Creator shares the link with all of their followers
4. Pledgers submit their payment information (via [Stripe](https://stripe.com/) or [MetaMask](https://metamask.io/)), but aren't charged until the deadline is reached

By the deadline, if the Minimum number of Pledgers is met:

5. Each pledger is charged (Target Amount)/(Number of Pledgers)
6. The Target Amount is sent to the Creator

Otherwise, if the Minimum Number of Pledgers isn't met:

5. Nothing happens; life goes on

## 👩‍💻 Developer Experience
_There are 3 levels developers can interface with PennySeed:_
1. Accessing the `<penny-seed></penny-seed>` [Web Component](https://www.webcomponents.org/) for a simple interface with the smart contract, using eventListeners and attributes.
2. Using the [Web3 API](https://web3js.readthedocs.io/en/1.0/) on the front-end to allow pledging and query campaign information
3. Using the [Web3 API](https://web3js.readthedocs.io/en/1.0/) on the [back-end](https://www.npmjs.com/package/web3) to add custom behavior to your campaign

## 👍 Benefits
✔️ Creators are guarenteed the Exact Amount they specify  
✔️ Pledgers are incentivized to share the Campaign to reduce their Pledge Share  
✔️ Minimal Design allows for a wide range of emergent applications and extensions  


## 🤔 Use Cases
__👩‍🎨 Artists__  
- Artists can use the base model to maintain a stable income  
- Content can be made free to the public, making it easier to gain more and more followers  
- Pledgers can access "bonus content" using their pledger id  
- Earlier pledgers can receive a "dividend" as later campaigns pay a percentage back, crowdsourcing "Content Curators" as people look for new artists to support early  
- Different "Pledge Types" can be defined, allowing some pledgers to license the Artist's content. If the Pledger is also a PennySeed user, they can forward a percentage of their Campaigns to the Original Artist's Campaign  

__🎫 Events__  
- A Campaign can be made to cover all costs of the Event (venue, catering, staff)  
- People can attend by Pledging, using their pledger id as a ticket  
- The more "tickets" are sold, the lower the ticket price, incentivizing pledgers to get others to attend  
- Different types of "tickets" can be defined, from selling individual days for multi-day events  
- A "Maximum Pledgers" can be specified to ensure not "too many" people attend  
- A "Minimum Pledger Age" can be specified if alcohol is involved  

__👩‍💻 API Developers__ 
- Like Artists, API developers can use the base model for a standard income
- Pledgers can use their pledge id as an API Access Key to use the API
- The Pledge Amount can be based on API usage

__📠 IoT Devices__  
- A Campaign can be made to cover the cost of the device (e.g. a Coffee Machine shared by a Coworking Space  
- People use the IoT device by pledging, using the pledger id to access the device  
- The Pledge Amount can be based on usage (pledge multiple times for multiple uses) or a single pledge for "full access"  
- The Campaign can be set to be the day before its return policy, allowing the Campaigner to return the IoT device when the Campaign isn't met  

__🏢 Coworking Spaces__  
- A Recurring Campaign can be made to cover the total cost of running the Space (Rent, Utilities, Staff, Insurance, Maintenance)  
- Pledgers can use their pledge id to access the CoWorking Space, encouraging more people to join to lower costs  
- Pledge costs can vary based on attendance or usage of provided IoT equipment  
- Events can be hosted in the Space, whose venue costs are coupled to the rent costs  
- Startups and Unemployeed attendees can pledge indirectly with future earnings  

__👩‍💼 Startup Funding__  
- Pledges can act as "shares"  
- A Recurring Campaign can forward a percent of Compaigns to past Campaign Pledgers, acing as a dividend  
- Product Startups can treat Pledges as Preorders, setting a Maximum number of Pledges for a fixed set of products  

## 📈 Revenue Model
  - PennySeed will have a recurring Campaign with a dividend extension for "investors"
  - All Campaigns pay a percent to a PennySeed fund
  - Revenue will come primarily from the former for initial funding, but as more campaigns are created revenue will come from the latter (a percentage of which will go back to the "investors")

## 🌎 Building a Community
  - Sponsoring Events by using PennySeed to fund the Events, including PennySeed Extension Hackathons
  - Provide a way for existing pledges from external sources to act as retroactive pledges
  - Provide a conventional payment method via Stripe, adding the [Stripe processing fee](https://stripe.com/pricing) (2.9% + $0.30 per pledge) on the pledger's end as an incentive to use a crypto wallet like [MetaMask](https://metamask.io/)
