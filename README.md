### INMO Whitepaper

#### Introduction

**INMO (inmo.xyz)** is a decentralized social platform designed to revolutionize the way users showcase their talents through videos and photos. By leveraging blockchain technology, INMO aims to provide a competitive environment where both consumers and creators can earn and win through engagement in challenges and competitions.

#### Problem Statement

Current social media platforms significantly limit monetization opportunities for most creators and brands due to restrictive algorithms and structural limitations. Only a small fraction of content creators and brands can monetize their content effectively.

#### Solution

INMO offers a blockchain-based, competition-driven social media platform available on iOS and Android. It enables creators to showcase their original content and get rewarded. Users can watch their favorite creators compete and also participate in competitions, fostering engagement on both sides. Initially developed as a hybrid web2/web3 solution on the Polygon blockchain, INMO has gained traction and aims to transition to a full web3 solution deployed on Arbitrum with appropriate funding.

#### Platform Overview

**Core Features:**
- **Challenges and Competitions:** Users can participate in various challenges by paying entry fees. The collected fees contribute to the reward pool.
- **Voting System:** Users vote for their favorite posts by paying voting fees, increasing the reward pool and fostering engagement.
- **Rewards:** Winners are rewarded based on their rankings, with the distribution of rewards managed by smart contracts.

#### Technical Architecture

**Smart Contract Design:**
The INMO platform relies on a series of smart contracts to manage posts, challenges, and reward distributions. Below is an overview of the core components and their interactions:

- **INMO Contract:**
  - Manages ERC20 token transactions.
  - Maps to store posts and challenges.
  - Functions include creating challenges, posting content, voting, and distributing rewards.

- **Challenge Configuration:**
  - Defines the parameters for each challenge, including reward amount, entry fees, voting fees, start and end dates, and payout structure.
  
- **Post Structure:**
  - Includes post ID, challenge ID, value, timestamp, and vote count.
  - Maps votes to user addresses.

**Smart Contract Functions:**
- **createChallenge:** Initializes a new challenge with specified configurations.
- **post:** Allows users to submit their posts to a challenge.
- **vote:** Enables users to vote on posts by paying voting fees.
- **payoutChallenge:** Distributes rewards based on votes and rankings.



### Smart Contract Logic

The essence of the smart contract is as follows:

- Any wallet with Challenge Creator privileges will be able to create a challenge.
- The creation of a challenge requires a USDC transfer for the reward amount, as well as the specification of:
  - Start and end dates of the challenge
  - Entry fees
  - Reward amount
  - Distribution percentages (totaling 100%) for payouts
- Once a challenge is created, INMO relinquishes any claim to the reward, and the smart contract takes over management of payouts.
- Any wallet can submit a post to a challenge, but unverified posts require validation by INMO before becoming eligible for the challenge.
- Submission of a post to a challenge requires an accompanying USDC entry fee.
- Users can vote on verified posts with a minimum voting fee.
- A post's "votes" correlate to the USDC it accumulates from voters, determining its ranking.
- In cases of tied "votes," the block number (proxy for time) of post creation is used for ranking, with later posts ranking higher.
- INMO will in the first phase reserve the authority to block any reported post, this can be expanded to a DOA in the future.
- If a post is blocked, voters will only receive their USDC back if the post ranks in the topN positions, forfeiting the percentage payout for that rank.
- If all posts in the topN are blocked, voter funds are returned, and the reward amount and entry fees are paid back to the challenge creator.
- When the challenge's end time arrives, anyone can initiate payouts by calling the adjudicate method on the contract.

It is important to note that payouts only credit the accounts of voters, posters, and the creator. Wallet owners will need to withdraw their funds from the smart contract, ensuring that only users have access to their funds. The creator (INMO) cannot access any credited USDC, as only the private key holder of the associated wallet account can withdraw the funds.


#### Milestones and KPIs

**Phase 1 (0-3 months):**
- **Mainnet Launch:** Transition INMO to Arbitrum for challenge payouts.
- **User Acquisition:** Achieve 10,000 active users.
- **Feature Rollout:** Implement and test smart contracts to transition INMO to a full web3 solution, optimizing core features like voting, leaderboard, and payment systems.

**Phase 2 (3-6 months):**
- **Scaling Up:** Expand user base to 50,000 active users.
- **Mainnet Launch:** Deploy INMO smart contracts to Arbitrum Mainnet.
- **Partnerships:** Form strategic partnerships with US universities and global influencers.
- **Enhanced Features:** Introduce multiple challenges and advanced features like personalized recommendations.

**Phase 3 (6-12 months):**
- **Global Expansion:** Launch marketing campaigns targeting new geographic regions.
- **Community Building:** Host community events and contests to drive engagement.
- **Revenue Growth:** Achieve monthly revenue targets of $100,000 through various monetization streams.

#### Conclusion

INMO represents a transformative approach to social media, leveraging blockchain technology to address the significant limitations of traditional platforms. By providing a decentralized, competition-driven environment, INMO enables content creators and consumers to engage in meaningful ways while offering real opportunities for monetization.

The platform’s robust technical architecture, built on the principles of smart contract functionality, ensures transparency, security, and fairness in the management of challenges and rewards. By transitioning to the Arbitrum ecosystem, INMO aims to enhance scalability, reduce transaction fees, and improve overall user experience.

The detailed milestones and phased approach outlined in this whitepaper underscore INMO’s commitment to growth and innovation. With strategic funding, INMO is poised to scale its user base, enhance feature offerings, and establish itself as a leading decentralized social platform.

INMO’s integration with Arbitrum not only facilitates its technical objectives but also aligns with broader ecosystem goals, contributing to the advancement of decentralized applications and blockchain adoption. The support from the Arbitrum Foundation will be pivotal in realizing INMO’s vision, driving user engagement, and setting new standards in social media monetization.

In summary, INMO is set to revolutionize the social media landscape by empowering creators and consumers with a transparent, rewarding, and engaging platform. The combination of innovative technology, strategic planning, and strong alignment with the Arbitrum ecosystem positions INMO for substantial impact and success in the decentralized space.