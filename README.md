# Handwritten Character Recognition (HCR) Using Artificial Neural Networks  

**A practical implementation of ANN-based character recognition with customizable workflows**  

This project demonstrates handwritten digit recognition using a simple yet effective Artificial Neural Network (ANN), designed for educational purposes and easy experimentation. Developed with Python and Jupyter Notebook, it serves as a foundational template for expanding into more complex character recognition tasks.  

---

## 🌟 Key Features  
- **ANN architecture** with customizable layers and activation functions  
- **MNIST dataset integration** (28x28 grayscale images of digits 0-9)  
- **Interactive Jupyter Notebook** with detailed code comments and visualizations  
- **Model performance metrics** including accuracy/loss graphs  
- **Export capability** for trained models  

---

## 🧠 Model Architecture  
**Core components**:  
- Input layer (784 neurons for 28x28 pixel images)  
- Hidden layers with ReLU activation (customizable depth)  
- Output layer with Softmax activation (10 classes for digits 0-9)  

**Training configuration**:  
- Adam optimizer with categorical cross-entropy loss  
- Batch normalization for stable training  
- Early stopping to prevent overfitting  

---

**Environment**:  
  Jupyter Notebook -  Google Colab  

---

## 🚀 Quick Start  
 
**installation**:  
```bash
git clone https://github.com/sruthivellore/HCR-Using-ANN.git
cd HCR-Using-ANN
pip install -r requirements.txt 
jupyter notebook
```

---

## 📊 Performance Metrics  
**Baseline results**:  
- Training accuracy: ~98%  
- Validation accuracy: ~97%  
- Loss convergence within 15 epochs  

---

## 🔍 Code Walkthrough  
**Key notebook sections**:  
1. **Data Preparation**:  
   - MNIST dataset loading  
   - Pixel normalization (0-255 → 0-1)  
   - One-hot encoding for labels  

2. **Model Building**:  
```python
model = Sequential([
    Flatten(input_shape=(28, 28)),
    Dense(512, activation='relu'),
    Dropout(0.2),
    Dense(10, activation='softmax')
])
```

3. **Training Configuration**:  
```python
model.compile(optimizer='adam',
              loss='categorical_crossentropy',
              metrics=['accuracy'])
```

4. **Evaluation**:  
   - Confusion matrix generation  
   - Sample predictions with visual comparison  


---

## 📚 Learning Resources  
- [MNIST Database](http://yann.lecun.com/exdb/mnist/) - Original dataset documentation  
- [TensorFlow ANN Guide](https://www.tensorflow.org/guide/keras) - Official Keras documentation  

---

**Happy coding!** ✨  
*"Every complex system begins as a simple prototype - here's yours for character recognition!"*  

