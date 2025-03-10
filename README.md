# ResNet18-Pruning-Performance
This project compares fine-grained vs. channel-level pruning on ResNet-18 trained on CIFAR-10 at pruning ratios 0.1, 0.3, and 0.5. Fine-grained pruning retains accuracy but lacks structured sparsity, while channel-level pruning improves efficiency but degrades accuracy. The study explores trade-offs between accuracy and computational performance.

---

# **ResNet-18 Pruning Performance Analysis**
**Fine-Grained vs. Channel-Level Pruning on CIFAR-10**

![GitHub Repo Badge](https://img.shields.io/badge/Deep_Learning-Pruning-blue)  
![GitHub Repo Badge](https://img.shields.io/badge/Framework-PyTorch-red)  
![GitHub Repo Badge](https://img.shields.io/badge/Status-Completed-brightgreen)  

## 📌 **Project Overview**
This project analyzes **fine-grained pruning** and **channel-level pruning** applied to a **ResNet-18** model trained on the **CIFAR-10 dataset**. The goal is to compare the impact of both pruning strategies on model accuracy and computational efficiency.  

Key findings reveal that:
- **Fine-grained pruning** retains higher accuracy but lacks structured sparsity for hardware acceleration.
- **Channel-level pruning** enables structured sparsity but suffers from larger accuracy degradation.
- **Pruning ratios (0.1, 0.3, 0.5) were tested** to analyze trade-offs between accuracy and efficiency.

---

## 🚀 **Project Highlights**
✅ **Baseline Model Performance:** Trained ResNet-18 on CIFAR-10 for 5 epochs (~80% accuracy).  
✅ **Fine-Grained Pruning:** Retains up to **80% accuracy** at low pruning ratios but lacks structured sparsity.  
✅ **Channel-Level Pruning:** More hardware-friendly but causes sharp accuracy drops (e.g., ~10% at 0.5 pruning ratio).  
✅ **Performance Graphs:** Accuracy vs. Pruning Ratio for both methods.  

---

## 📂 **Project Structure**
```
📁 ResNet18-Pruning-Performance
│── 📂 data/                # Dataset (CIFAR-10 downloaded automatically)
│── 📂 models/              # Model checkpoint storage
│── 📂 results/             # Accuracy vs. Pruning Ratio graphs
│── 📜 train.py             # Train ResNet-18 model on CIFAR-10
│── 📜 prune.py             # Apply fine-grained & channel-level pruning
│── 📜 evaluate.py          # Evaluate model performance
│── 📜 requirements.txt     # Dependencies (PyTorch, torchvision, numpy, matplotlib)
│── 📜 README.md            # Project documentation (this file)
```

---

## 📊 **Results & Observations**
### **1️⃣ Baseline Performance**
- **ResNet-18 trained for 5 epochs** on CIFAR-10 reached **~80% accuracy** before pruning.

### **2️⃣ Fine-Grained Pruning Results**
| Pruning Ratio | Accuracy (%) |
|--------------|--------------|
| 0.1 (10%)    | ~80% |
| 0.3 (30%)    | ~75%-78% |
| 0.5 (50%)    | ~50%-55% |

- **Key Observation**: Fine-grained pruning maintains accuracy for low pruning ratios but experiences sharp drops at 0.5.

### **3️⃣ Channel-Level Pruning Results**
| Pruning Ratio | Accuracy (%) |
|--------------|--------------|
| 0.1 (10%)    | ~40%-45% |
| 0.3 (30%)    | ~20%-25% |
| 0.5 (50%)    | ~10%-15% |

- **Key Observation**: Channel-level pruning significantly reduces accuracy, making it less suitable for accuracy-critical applications.

### **4️⃣ Accuracy vs. Pruning Ratio Graph**
![Accuracy vs Pruning Ratio](results/accuracy_vs_pruning.png)

---

## 🛠 **Installation & Usage**
### **1️⃣ Install Dependencies**
Clone the repository and install the required dependencies.
```bash
git clone https://github.com/Yeshwant-Kasa/ResNet18-Pruning-Performance.git
cd ResNet18-Pruning-Performance
pip install -r requirements.txt
```

### **2️⃣ Train the Baseline Model**
Run the training script to train ResNet-18 on CIFAR-10 for 5 epochs.
```bash
python train.py
```

### **3️⃣ Apply Pruning**
#### **Fine-Grained Pruning**
```bash
python prune.py --method fine --ratio 0.3
```
#### **Channel-Level Pruning**
```bash
python prune.py --method channel --ratio 0.3
```

### **4️⃣ Evaluate Pruned Models**
```bash
python evaluate.py
```

---

## 🔍 **Key Takeaways**
1. **Fine-Grained Pruning** → Best for **accuracy-sensitive** applications but lacks structured sparsity.  
2. **Channel-Level Pruning** → Best for **resource-limited** devices but sacrifices accuracy.  
3. **Future Work** → Hybrid pruning strategies may balance accuracy and efficiency.

---

## 📌 **Future Work**
- 🔍 **Fine-tuning** post-pruning to recover accuracy.
- ⚡ **Hybrid pruning strategies** (combining fine-grained and channel pruning).
- 📈 **Testing with deeper models** (e.g., ResNet-50, VGG16).
- 🚀 **Deployment optimizations** using TensorRT for efficient inference.

---

## 🤝 **Contributing**
Contributions are welcome! If you'd like to improve this project:
1. **Fork the repository**.
2. **Create a new branch** (`feature-branch`).
3. **Commit your changes**.
4. **Submit a pull request**.

---

## 📜 **License**
This project is licensed under the **MIT License**.

---

## 👨‍💻 **Author**
📌 **Kasa Yeshwant** – *Sensor Optimization, App Development with Android Studio-Koala, Machine Learning Researcher & AI Enthusiast*  
📧 [yeshwantkasa@gmail.com](mailto:your.email@example.com)  
🌍 [GitHub Profile](https://github.com/Yeshwant-Kasa)

---


