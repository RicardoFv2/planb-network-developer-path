# Flashcards: Where Bitcoin (Class 3)

> Use these for Active Recall. Try to answer before looking at the solution.

---

### Q1: What is the "Timechain" in Bitcoin?

**A:** Bitcoin is better understood as a "Timechain" because its primary function is to act as a decentralized clock. It solves the **Double Spend Problem** by providing a globally agreed-on chronological order of transactions.

---

### Q2: How does the "Newspaper Analogy" explain Bitcoin blocks?

**A:** Just as a kidnapper holds a today's newspaper in a photo to prove it was taken _after_ the newspaper was printed, the data inside a Bitcoin block proves that it existed at a specific point in time relative to the rest of the chain.

---

### Q3: What is "Unforgeable Costliness" in the context of Proof of Work?

**A:** It means that the "truth" of the ledger is backed by real-world energy. You cannot fake energy expenditure; therefore, Proof of Work is like a digital stamp of truth that requires significant physical cost to create or rewrite.

---

### Q4: What is the "Difficulty Adjustment" often called, and what does it do?

**A:** Often called the **"Heartbeat"** or **"Internal Thermostat"** of Bitcoin. It adjusts the difficulty of mining every 2,016 blocks (~2 weeks) to ensure that blocks are found every 10 minutes on average, regardless of how much mining power joins or leaves.

---

### Q5: What is the "Sigma Equation" ($\Sigma$)?

**A:** It represents Bitcoin's fixed monetary policy. It dictates the cap of 21 million BTC and the **Halving** mechanism, where the issuance of new bitcoin is cut in half approximately every 4 years (210,000 blocks).

---

### Q6: Contrast "Subsidy" vs "Fees" in mining economics.

**A:** The **Subsidy** is new bitcoin created with every block (currently the main source of miner revenue). **Fees** are paid by users to have their transactions included. As the subsidy halves toward zero, fees become the primary incentive for miners to secure the network.

---

### Q7: Explain the "Scaling Trilemma" trade-offs.

**A:** It's the challenge of achieving **Decentralization**, **Security**, and **Scalability (Throughput)** at the same time. Bitcoin prioritizes Decentralization and Security at its base layer, electing to scale its throughput (Scalability) via higher layers.

---

### Q8: What is the "Bathtub Curve" analogy for block size?

**A:** If you increase the flow of data (water) into the network (the tub) with a small drain (the hardware limits of an average user's node), the tub overflows. Increasing block size indefinitely leads to centralization because only giant data centers could "drain" (process) the data.

---

### Q9: How does the Lightning Network scale Bitcoin payments?

**A:** By using **off-chain payment channels**. Users lock funds on-chain once, and then transact instantly and for free off-chain. Only the net result of thousands of transactions is settled back onto the Timechain.

---

### Q10: What is "Gresham's Law" in the context of Bitcoin adoption?

**A:** The principle that "Bad money drives out good money." People prefer to spend their rapidly depreciating fiat currency and "hoard" their sound money (Bitcoin). This is why Bitcoin is viewed as a Store of Value (SoV) before it becomes a common Medium of Exchange (MoE).

---

### Q11: What is the "Double Spend Problem"?

**A:** The ability to spend the same digital token twice. Since digital data is trivial to copy, decentralized systems need a canonical history (the Timechain) to verify that a coin hasn't already been spent by its owner.

---

### Q12: What role do Merkle Trees play in a Bitcoin block?

**A:** They allow for efficient content verification. By hashing all transactions in a block into a single "Merkle Root," users can prove a transaction is part of a block without needing to download the entire block's data.

---

### Q13: How does network latency affect decentralized consensus?

**A:** Due to the speed of light limits, different parts of the world see events at slightly different times. Without a "decentralized clock" like the Timechain, there would be no way for nodes across the globe to agree on which transaction happened first.

---

### Q14: What defines the "True History" in Bitcoin?

**A:** The chain with the most **cumulative Proof of Work** is accepted by all nodes as the true and valid history of the network. This makes rewriting history exponentially more difficult and expensive as time passes.

---

### Q15: What are PTLCs and why are they an improvement over HTLCs?

**A:** **Point Time Locked Contracts** (PTLCs) improve privacy in the Lightning Network by allowing for "payment decorrelation." Unlike HTLCs (Hash Time Locked Contracts), intermediate nodes cannot easily see they are part of the same payment route.

---

### Q16: In the Bathtub analogy, what does the "Outlet" represent?

**A:** The "Outlet" represents the **resource constraints** of an individual participant's computer (bandwidth, CPU, and storage). If the "Inlet" (on-chain data) is larger than the "Outlet," the participant can no longer verify the network independently.

---

### Q17: How does increased block size lead to centralization?

**A:** Larger blocks increase the threshold of hardware required to run a full node. If it becomes too expensive for individuals to verify the blockchain, only a few large data centers will run nodes, making the network easy to control and censor.

---

### Q18: Why is Bitcoin considered a Store of Value (SoV) before a Medium of Exchange (MoE)?

**A:** Because humans naturally hoard assets they believe will increase in value (hard money) while spending assets that lose value (weak money). This is an expression of Gresham's Law.

---

### Q19: What is the role of stablecoins like USDT in the context of adoption?

**A:** They act as a "bridge" for regulatory arbitrage. They prove that censorship-resistant rails (like Bitcoin or other distributed networks) provide global value even for traditional, fiat-denominated assets.

---

### Q20: What is a "VTXO" in the Ark protocol?

**A:** A **Virtual UTXO**. It represents funds held off-chain within the Ark layer. Users can transfer these VTXOs instantly and privately without the need to manage individual Lightning payment channels.

---

[[index|Return to Index]]
