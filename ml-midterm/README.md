>## Midterm project:   Classification Analysis - Titanic Dataset

**Author:** Dinesh Gurumoorthy  
**Date:** November 11, 2025  

### Notebook link: https://github.com/dineshgurum8/applied-ml-dineshguru/blob/main/ml-midterm/classification_dineshguru.ipynb

### Peer Review link: https://github.com/dineshgurum8/applied-ml-dineshguru/blob/main/ml-midterm/peer_review.md 




#### Feature Engineering & Selection

**Case 1: Simple Binary Feature**
- **Features**: `alone` (binary: traveling alone vs. with family)
- **Rationale**: Test social dynamics theory in survival scenarios
- **Analysis**: 50.6% survival with family vs. 30.4% alone

**Case 2: Continuous Demographic Feature** 
- **Features**: `age` (continuous numerical)
- **Rationale**: Age represents physical capability and social priority ("children first")
- **Analysis**: Clear age patterns - Children (58.0%), Adults (35.3%), Seniors (22.7%)

**Case 3: Complex Feature Interaction**
- **Features**: `age` + `family_size` (multi-dimensional)
- **Rationale**: Combine demographic and social context factors
- **Analysis**: Family sizes 2-4 show 55-72% survival vs. 30% for solo travelers

### Performance Summary - Classification Results

| Model Type | Case | Features Used | Accuracy | Precision | Recall | F1-Score | Notes |
|------------|------|---------------|----------|-----------|--------|----------|-------|
| **Decision Tree** | 1 | alone | **63%** | 61% | 62% | 61% | 🏆 Best generalization, minimal overfitting |
| | 2 | age | 61% | 57% | 53% | 50% | Poor survivor recall (17%) |
| | 3 | age + family_size | 59% | 55% | 54% | 54% | Significant overfitting evident |
| **SVM (RBF)** | 1 | alone | **63%** | 61% | 62% | 61% | Matches Decision Tree performance |
| | 2 | age | 63% | 67% | 53% | 45% | ⚠️ Terrible survivor recall (7%!) |
| | 3 | age + family_size | 63% | 67% | 53% | 45% | No improvement from added features |
| **Neural Network** | 3 | age + family_size | **66%** | 64% | 62% | 63% | 🏆 Highest accuracy achieved |

#### **🏆 Performance Rankings:**
1. **Neural Network (Case 3)**: 66% accuracy - Best overall performance
2. **Decision Tree & SVM (Case 1)**: 63% accuracy - Tied for simple features  
3. **Decision Tree (Case 2)**: 61% accuracy - Moderate performance

### Technical Accomplishments

- **Multi-Algorithm Implementation**: Successfully deployed three different ML algorithms
- **Systematic Feature Testing**: Rigorous evaluation across multiple feature combinations
- **Model Comparison**: Comprehensive performance analysis with multiple metrics
- **Overfitting Detection**: Identified and analyzed training vs. test performance gaps
- **Visualization Techniques**: Decision trees, support vectors, and neural network decision boundaries
- **Class Imbalance Handling**: Proper stratified train/test splitting

### Key Learning Outcomes & Insights

#### **Critical Discovery: Model-Feature Complexity Matching**

1. **Simple Features → Simple Models**: Decision Tree and SVM excel with basic features (`alone`)
2. **Complex Features → Advanced Models**: Neural Networks perform best with feature interactions
3. **Feature Addition Paradox**: More features can hurt simple models but help complex ones

#### **Algorithm-Specific Insights**

- **Decision Trees**: Most reliable across all cases, best for interpretability
- **SVM**: Excellent for simple features but struggles with class imbalance on complex features  
- **Neural Networks**: Superior for complex feature relationships, requires proper architecture

#### **Practical Machine Learning Lessons**

1. **Overfitting Patterns**: Training accuracy ≠ real-world performance
2. **Evaluation Metrics**: Accuracy alone insufficient - examine precision/recall individually
3. **Feature Engineering Impact**: Quality over quantity in feature selection
4. **Algorithm Selection**: Match model sophistication to data complexity

## Update this README as you work

Add commands to run additional scripts as you work through the course (update the path and file name as needed).

---

### 3.5 Git add-commit-push to GitHub

Anytime we make working changes to code is a good time to git add-commit-push to GitHub.

1. Stage your changes with git add.
2. Commit your changes with a useful message in quotes.
3. Push your work to GitHub.

```shell
git add .
git commit -m "describe your change in quotes"
git push -u origin main
```

This will trigger the GitHub Actions workflow and publish your documentation via GitHub Pages.

### 3.6 Modify and Debug

With a working version safe in GitHub, start making changes to the code.

Before starting a new session, remember to do a `git pull` and keep your tools updated.

Each time forward progress is made, remember to git add-commit-push.
