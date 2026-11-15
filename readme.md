# 🕵️ SAMPLING DETECTIVE: The Mystery of Missing Data
**Interactive 3D Game for Learning Data Science Concepts**

🔗 **Play the Live Game Here (GitHub Pages)**

IIITDM KANCHEEPURAM

Kalapati Balaji —- EC24B1054

## 1. Defined Learning Objectives & Concept Coverage
This game teaches fundamental Data Science sampling concepts through an interactive 3D environment and active experimentation, rather than static quizzes:

**1. Population vs. Sample & The Impact of Sample Size (Levels 1 & 2):**
*   **Concept:** Estimating a population mean $\mu$ using a sample mean $\bar{x}$. As sample size $n$ increases, the sampling variability and absolute sampling error $|\bar{x} - \mu|$ generally decrease.
*   **Discovery Outcome:** Learners interact with the Random Terminal, generating actual random samples of $n=10$, $50$, and $200$. They visually discover via Chart.js graphs that small samples result in wildly fluctuating means, while larger samples converge closer to the true population mean.

**2. Structured Representation: Systematic & Stratified Sampling (Level 3):**
*   **Concept:** Pure random sampling can sometimes miss minority groups. Stratified sampling ensures proportional representation across subgroups (e.g., City Zones: North, South, East), reducing variance. Systematic sampling provides an alternative using a randomized starting point and selecting every $k$-th record.
*   **Discovery Outcome:** Learners run simulations comparing these methods for $n=50$. They discover that Stratified sampling often yields a consistently lower absolute error than Simple Random sampling when the data is heavily influenced by regional demographics.

**3. The Danger of Sampling Bias (Level 4 & 5):**
*   **Concept:** A biased sampling frame (Convenience Sampling / Selection Bias) cannot be fixed simply by increasing the sample size.
*   **Discovery Outcome:** Learners are presented with a "Mayor's Survey" of $n=300$ citizens that exclusively polled car owners. They discover that despite the massive sample size, the resulting mean is heavily skewed. In Level 5, they must actively choose to avoid biased methods to secure a high score.

---

## 2. How-to-Play Guide & Game Mechanics

### Running the Game
*   **Option A (Web):**🔗 Play the Live Game Here (GitHub Pages)**

*   **Option B (Local):** Clone this repository and open `sampling_detective.html` directly in any modern browser (zero external Python/Node dependencies required).

### Gameplay Loop & Rules
*   **Goal:** You are a Data Science Detective. A city database has 1,000 citizens. You must use statistical sampling across 3 dynamic Cases (Traffic, Economy, Happiness) to estimate hidden population means without analyzing every record.
*   **The 3D Investigation:** 
    1. Use **W, A, S, D** or **Arrow Keys** to navigate the 3D Police Precinct.
    2. Follow the floating yellow marker to your next objective.
    3. Approach characters/terminals and press **[E]** to interact.
*   **The 5 Levels (Per Case):**
    *   **Level 1 (The Chief):** Get your briefing and understand the Population.
    *   **Level 2 (Blue Terminal):** Experiment with Simple Random Sampling sizes.
    *   **Level 3 (Green Terminal):** Test Systematic and Stratified algorithms.
    *   **Level 4 (Red Terminal):** Identify and analyze the rigged/biased dataset.
    *   **Level 5 (Gold Mainframe):** The final test. You must select the optimal sampling method and size to estimate the true mean. Picking a biased method or a tiny sample will result in high error and a low score.
*   **Evidence of Learning:** Upon completing all 3 cases, the game presents a "Detective's Field Notes" screen where playtesters can type their statistical findings. This can be directly printed to a PDF as proof of playtesting.

---

## 3. Technical Implementation & Real Computation

*   **Dynamic Simulation Engine:** All outcomes are generated dynamically per session. The game utilizes a seeded JavaScript generator to create a living population of 1,000 synthetic citizen records (with attributes like Age, Zone, Car Ownership, and target metrics). **No answers or means are hard-coded.**
*   **Algorithms Implemented in JavaScript:**
    *   **Population Mean:** $\mu = \frac{\sum x_{i}}{N}$
    *   **Sample Mean:** $\bar{x} = \frac{\sum x_{i}}{n}$
    *   **Absolute Error:** $|\bar{x} - \mu|$
    *   **Stratified Proportional Allocation:** $n_{h} = n \times (\frac{N_{h}}{N})$
*   **3D & Visualization Engine:** 
    *   **Three.js** drives the interactive low-poly 3D world, featuring animated characters, dynamic lighting that changes per case, and spatial interactions.
    *   **Chart.js** renders real-time statistical comparisons comparing the Population $\mu$ against the Sample $\bar{x}$.

---

## 4. Playtest Evidence & Learner Outcomes

*(Note: Raw telemetry and printed PDF reports from the in-game "Field Notes" feature are stored in the `/playtest_evidence` folder).*

### Summary of Peer Playtest Telemetry

| Peer / Roll No | Case 1 Strategy (Traffic) | Level 4 Bias Trap | Final Score (Max 600) | Usability (1–5) | Key Takeaway Reported by Peer |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Peer 1 (SUDEEP)** | Chose Random, $n=20$ | Triggered Trap | 450 | 5 / 5 | "I learned that increasing sample size doesn't fix a bad methodology. The biased $n=300$ had worse error than random $n=50$." |
| **Peer 2 (CHANDU)** | Chose Stratified, $n=100$ | Spotted Trap | 580 | 5 / 5 | "Stratified sampling gave me incredibly low error on the Economy case because it accounted for the rich 'North' zone perfectly." |
| **Peer 3 (MAHESH)** | Chose Biased, $n=400$ | Fell for Trap | 300 | 4 / 5 | "I thought picking the biggest sample ($n=400$) at the end would guarantee a win, but I accidentally picked the biased method and lost points." |
