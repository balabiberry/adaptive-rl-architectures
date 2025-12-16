# Adaptive RL Architectures

Adaptive Neural Architecture Search (NAS) for Reinforcement Learning agents using **PPO** in the **DeepMind Control Suite (Cheetah)**.

The system automatically selects neural network architectures based on performance, reducing manual tuning and computational cost.  
Applicable to **robotics**, **autonomous systems**, and **AI research**.

---

## 📌 Project Goals

- Automate neural architecture selection for RL agents  
- Reduce manual hyperparameter tuning and computational overhead  
- Improve performance in dynamic and complex environments  

---

## 🧩 Key Concepts

- **Neural Architecture Search (NAS)**  
A recurrent LSTM-based controller generates candidate architectures by varying:
  - number of layers  
  - layer sizes  
  - activation functions  

- **Reinforcement Learning (RL)**  
Agents are trained using **Proximal Policy Optimization (PPO)** on the generated architectures.

- **Closed Training Loop**  
Architectures are generated → agents are trained → rewards are evaluated → controller is updated.

---

## ⚙️ Architecture Parameters

- **Number of layers:** 1 to 5  
- **Layer sizes:** 64, 128, 256  
- **Activation functions:** ReLU, Leaky ReLU, Swish  

### Example Generated Architecture

```json
{
  "layers": [128, 256, 256],
  "activation": "Swish"
}
```


---

## 🚀 Training Flow

1. NAS controller generates candidate neural architectures  
2. PPO agent is trained on each candidate for a short training cycle  
3. Architectures are evaluated based on average reward  
4. Top-performing architectures are selected  
5. Selected architectures undergo longer training for evaluation  
6. Controller is updated and the loop repeats  

---

## 📊 Metrics & Evaluation

- **Primary metric:** Average reward over training steps  
- Training data and results are serialized to JSON for reproducibility  
- Architecture filtering avoids redundant or weak candidates  

**Best result:**  
> Achieved **>5.5 average reward at 5,000 steps**  
> (~55% improvement over baseline architecture)

---

## 📈 Results

- Significant improvement over baseline architectures  
- Efficient candidate filtering reduced overall training cost  
- Confirmed generalization across different random seeds  
- Demonstrated robustness and training stability  

---

## 🔮 Future Work

- Expand to additional agents and environments  
- Integrate more advanced NAS and meta-learning techniques  
- Apply the system to real-world robotics and autonomous navigation tasks  

---

## 🛠️ Technologies Used

- Python  
- PyTorch  
- DeepMind Control Suite (`dm_control`)  
- Proximal Policy Optimization (PPO)  
- LSTM-based NAS controller  

---

## 📂 Project Structure

```text
adaptive-rl-architectures/
├── nas_controller/         # LSTM-based architecture generator
├── ppo_agent/              # PPO training logic
├── environments/           # DM Control Suite integration
├── data/                   # JSON logs and architecture metrics
└── utils/                  # Helper functions and visualization tools
```

---

👤 Author
S. O. Balaba 

Supervisor: Assoc. Prof. M. V. Holovyanko
