# **Graph Neural Network-Based Silicosis Detection**

This repository contains the implementation of a **Graph Neural Network (GNN)**-based framework for detecting silicosis from chest X-ray images. The method involves dividing each lung into multiple regions, constructing graph representations, processing them using GNNs, and combining the results for holistic predictions.

---

## **Process Description**

### **1. Node Creation**
- Each lung (left and right) is divided into **six regions** based on anatomical significance (e.g., upper, middle, and lower lung zones).
- Each region is represented as a **node** in the graph.
- Features for each node are extracted from the corresponding image region, such as:
  - **Pixel intensity statistics**
  - **Texture features**
  - **Deep learning-based embeddings**

### **2. Graph Construction**
- Nodes (lung regions) within the same lung are connected based on:
  - Spatial adjacency
  - Anatomical relevance
- **Edges** represent relationships such as:
  - Shared borders
  - Spatial proximity
  - Functional correlation
- Separate graphs are constructed for the **left lung** and the **right lung**.

### **3. Graph Neural Network (GNN) Processing**
- A GNN model (e.g., Graph Convolutional Network, Graph Attention Network) is applied to the left and right lung graphs independently.
- The GNN learns to propagate information across nodes and edges, capturing interdependencies between lung regions.

### **4. Result Concatenation**
- The outputs from the left and right lung GNNs are **concatenated** to create a unified feature vector.
- This combined representation encodes the overall state of both lungs.

### **5. Classification**
- The concatenated features are passed through a **classification layer** to predict:
  - The presence of silicosis.
  - The severity of silicosis.
- This step integrates information from both lungs for a comprehensive diagnosis.

---.
