# Contributing to Heart Disease Prediction Project

Thank you for your interest in contributing to the Heart Disease Prediction Project! This document provides guidelines for contributing to this project.

## Table of Contents

- [Code of Conduct](#code-of-conduct)
- [Getting Started](#getting-started)
- [How to Contribute](#how-to-contribute)
- [Development Setup](#development-setup)
- [Coding Standards](#coding-standards)
- [Submitting Changes](#submitting-changes)
- [Reporting Issues](#reporting-issues)

## Code of Conduct

This project adheres to a code of conduct that we expect all contributors to follow. Please be respectful and professional in all interactions.

## Getting Started

1. **Fork the repository** on GitHub
2. **Clone your fork** locally:
   ```bash
   git clone https://github.com/yourusername/CapstoneProject.git
   cd CapstoneProject
   ```
3. **Create a virtual environment**:
   ```bash
   python -m venv venv
   source venv/bin/activate  # On Windows: venv\Scripts\activate
   ```
4. **Install dependencies**:
   ```bash
   pip install -r requirements.txt
   ```

## How to Contribute

### Types of Contributions

- **Bug fixes**: Fix issues in the existing code
- **Feature enhancements**: Add new functionality
- **Documentation improvements**: Enhance README, comments, or documentation
- **Performance optimizations**: Improve model performance or code efficiency
- **Testing**: Add or improve test coverage

### Areas for Contribution

1. **Model Improvements**:
   - Experiment with new algorithms
   - Improve feature engineering
   - Enhance hyperparameter tuning

2. **Code Quality**:
   - Refactor code for better readability
   - Add error handling
   - Improve logging and monitoring

3. **Documentation**:
   - Add code comments
   - Improve README
   - Create tutorials or examples

4. **Deployment**:
   - Create REST API
   - Add Docker support
   - Cloud deployment scripts

## Development Setup

### Prerequisites

- Python 3.8 or higher
- Git
- Jupyter Notebook

### Installation

1. Follow the [Getting Started](#getting-started) steps
2. Install development dependencies:
   ```bash
   pip install -r requirements-dev.txt  # If available
   ```
3. Run the notebook to ensure everything works:
   ```bash
   jupyter notebook heart-disease/notebook/heart_disease_prediction.ipynb
   ```

## Coding Standards

### Python Code Style

- Follow **PEP 8** guidelines
- Use **meaningful variable names**
- Add **docstrings** for functions and classes
- Keep **functions focused** and modular
- Add **type hints** where appropriate

### Notebook Guidelines

- **Clear cell structure**: One logical operation per cell
- **Markdown documentation**: Explain what each section does
- **Remove output** before committing (except for demonstration purposes)
- **Consistent formatting**: Use consistent naming and structure

### Example Code Style

```python
def predict_heart_disease_risk(patient_data: dict, return_probability: bool = True) -> dict:
    """
    Predict heart disease risk for a patient.
    
    Args:
        patient_data (dict): Dictionary containing patient features
        return_probability (bool): Whether to return probability scores
        
    Returns:
        dict: Prediction results including risk level and confidence
    """
    # Implementation here
    pass
```

## Submitting Changes

### Pull Request Process

1. **Create a feature branch**:
   ```bash
   git checkout -b feature/your-feature-name
   ```

2. **Make your changes** following the coding standards

3. **Test your changes**:
   - Run the notebook end-to-end
   - Verify no errors or warnings
   - Check that outputs are reasonable

4. **Commit your changes**:
   ```bash
   git add .
   git commit -m "Add: Brief description of your changes"
   ```

5. **Push to your fork**:
   ```bash
   git push origin feature/your-feature-name
   ```

6. **Create a Pull Request** on GitHub

### Commit Message Guidelines

- Use the format: `Type: Brief description`
- Types: `Add`, `Fix`, `Update`, `Remove`, `Refactor`, `Doc`
- Examples:
  - `Add: New feature engineering technique for BMI categories`
  - `Fix: Handle missing values in age column`
  - `Update: Improve model performance with better hyperparameters`
  - `Doc: Add examples for prediction functions`

### Pull Request Guidelines

- **Descriptive title**: Clearly describe what the PR does
- **Detailed description**: Explain the changes and why they were made
- **Reference issues**: Link to related issues if applicable
- **Include screenshots**: For UI changes or new visualizations
- **Test results**: Include performance metrics if relevant

## Reporting Issues

### Bug Reports

When reporting bugs, please include:

1. **Clear title**: Summarize the issue
2. **Steps to reproduce**: Detailed steps to recreate the bug
3. **Expected behavior**: What you expected to happen
4. **Actual behavior**: What actually happened
5. **Environment**: Python version, OS, package versions
6. **Screenshots**: If applicable

### Feature Requests

For feature requests, please include:

1. **Clear description**: What feature you'd like to see
2. **Use case**: Why this feature would be useful
3. **Possible implementation**: Any ideas on how to implement it
4. **Alternatives**: Other solutions you've considered

### Issue Labels

- `bug`: Something isn't working
- `enhancement`: New feature or request
- `documentation`: Improvements or additions to documentation
- `good first issue`: Good for newcomers
- `help wanted`: Extra attention is needed

## Development Guidelines

### Testing

- **Test your changes** thoroughly before submitting
- **Run the entire notebook** to ensure no breaking changes
- **Verify model performance** hasn't degraded
- **Check edge cases** and error handling

### Performance Considerations

- **Memory efficiency**: Be mindful of memory usage with large datasets
- **Processing time**: Optimize for reasonable execution times
- **Scalability**: Consider how changes affect scalability

### Documentation

- **Update README**: If adding new features
- **Add comments**: Explain complex logic
- **Update docstrings**: Keep function documentation current
- **Include examples**: Show how to use new features

## Questions and Support

If you have questions or need help:

1. **Check existing issues** for similar questions
2. **Create a new issue** with the `question` label
3. **Contact maintainers** through GitHub issues

## Recognition

Contributors will be recognized in:
- **README acknowledgments** section
- **Release notes** for significant contributions
- **Contributors list** on GitHub

Thank you for contributing to the Heart Disease Prediction Project!
