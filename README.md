# Student Performance Prediction Using Linear Algebra

This repository contains a mini-project that implements core **Linear Algebra (LAA)** concepts to analyze, clean, and extract patterns from a real-world dataset of student grades across multiple academic subjects. 

Rather than relying on black-box machine learning libraries, this project utilizes foundational matrix operations to discover feature dependencies, reconstruct missing information, and find orthogonal bases.

---

## 📊 Linear Algebra Concepts Implemented

The project progresses through structured steps, mapping directly to fundamental linear algebra principles:

### 1. Matrix Representation & Vector Spaces
* **Implementation:** Tabular CSV data is converted into a numeric NumPy matrix $A$ of dimensions $20 \times 8$ (representing 20 students as vectors in an 8-dimensional subject space).

### 2. Matrix Simplification using RREF
* **Implementation:** Computed the **Reduced Row Echelon Form (RREF)** of the data matrix using `sympy`. This determines whether columns (subjects) are linearly independent and identifies the pivot columns.

### 3. Dimension Analysis (Rank & Nullity)
* **Implementation:** Calculated the matrix rank ($\text{Rank} = 8$) and nullity ($\text{Nullity} = 0$). By the **Rank-Nullity Theorem**, a rank of 8 confirms that all subjects span an 8-dimensional space with zero redundant dimensions.

### 4. Orthogonalization via QR Decomposition
* **Implementation:** Factored the matrix $A$ into an orthogonal matrix $Q$ and an upper triangular matrix $R$ ($A = QR$). Matrix $Q$ provides an **orthonormal basis** for the column space, filtering out correlation noise.

### 5. Vector Projection
* **Implementation:** Projected an individual subject vector onto the orthonormal subspace using $P = QQ^T$, confirming that the orthonormal basis accurately preserves original geometries.

### 6. Data Imputation via Least Squares Approximation
* **Implementation:** Handled missing grades (`NaN`) by setting up an overdetermined system $Ax \approx b$. Using `np.linalg.lstsq`, it minimizes the residual vector norm to predict missing elements based on existing cross-subject correlations.

### 7. Covariance & Spectral Decomposition (Eigenvalues/Eigenvectors)
* **Implementation:** Diagonalized the covariance matrix ($A = VDV^{-1}$) to solve for eigenvalues and eigenvectors, exposing the principal components and dominant directions of variation in student profiles.

---

## 🛠️ Tech Stack & Dependencies

* **Python 3.x**
* **NumPy** (Matrix manipulations, QR decomposition, Least Squares, and Eigenvalues)
* **Pandas** (Data loading and handling structural matrices)
* **SymPy** (Exact symbolic computation of the RREF matrix)

---

## 📁 Repository Structure

* `student_marks1.csv`       # Dataset containing student grades with missing elements
* `LAA_MiniProject1.ipynb`   # Complete Google Colab notebook walkthrough
* `README.md`                # Project documentation and LAA concept mapping
