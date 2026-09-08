# internship
Design and analysis of control schemes for DAB converter for charging applications
📌 Project Overview
This repository contains the final project report for my research internship. The project focuses on controlling a Dual Active Bridge (DAB) converter for Electric Vehicle (EV) battery charging.

The entire system, including the power circuits and the controllers, was designed and simulated using MATLAB and Simulink.

The converter operates at a high switching frequency of 100 kHz. Because fast switching can cause noisy current ripples and voltage spikes that harm battery life, this study compares traditional control methods against modern Artificial Intelligence (AI) methods to achieve the smoothest and safest charging profile.

📂 Repository Contents
Project_Report.pdf: A detailed document covering the background, methods, and simulation results.

README.md: This project summary.

(Note: The actual MATLAB/Simulink simulation files are not included in this public repository).

🎛️ Control Schemes Analyzed
We built and tested three different control setups in Simulink to see which one performed the best:

Classical PI Controller: The standard, traditional method. It regulates the power but suffers from high current ripples.

PI Controller with ANN: An Artificial Neural Network is added to help the PI controller react much faster to changes.

PI Controller with RNN-LSTM: A Recurrent Neural Network is used to track power trends over time, providing the most stable control.

🧠 RNN vs. ANN for This Work
In this project, the ANN and RNN handle the battery data very differently. The ANN (Artificial Neural Network) works by looking at a single "snapshot" of data—it only looks at the exact error happening at this exact microsecond and immediately guesses the correction. This makes it very fast, but it can sometimes cause small jitters in the power.

The RNN (Recurrent Neural Network), on the other hand, has a built-in memory. Instead of looking at a single snapshot, it looks at a continuous sequence of past data to understand the trend of the voltage and current. Because the RNN remembers what happened a few moments ago, it predicts the corrections much more smoothly. This memory feature allows the RNN to completely eliminate the high-frequency jitters that the ANN struggles with.

📊 Key Findings
Better Power Quality: The AI controllers significantly reduced the current ripples compared to the traditional PI setup. The RNN performed the best overall.

Battery Protection: By smoothing out the power profile and removing spikes, the AI models ensure much safer charging and better long-term health for EV batteries.
