
# **Step-by-Step Guide to Creating and Using a Conda Environment**

This guide walks you through setting up a **Conda environment** from scratch, activating it, and ensuring it works properly in **Mac and Windows**.

---

## **📌 1. Install Conda (If Not Installed)**
Before creating an environment, ensure you have **Anaconda** installed.

### **Check if Conda is Installed**
Open a terminal (Mac/Linux) or **Anaconda Prompt** (Windows) and run:

```sh
conda --version
```

Expected output (version may vary):

```
conda 24.1.2
```

If Conda is **not installed**, download and install **Anaconda**:

- **[Anaconda Download](https://www.anaconda.com/products/distribution)**

After installation, restart your terminal.

---

## **📌 2. Verify Conda Installation**
To ensure Conda is installed and working:

```sh
conda info
```

This will output information about your Conda setup.

---

## **📌 3. Create an `environment.yml` File**
A **YAML** file (`environment.yml`) specifies the environment name and dependencies.

### **Create the File**
1. Open a terminal (Mac/Linux) or **Command Prompt** (Windows).
2. Navigate to the folder where you want to save the file (optional).
3. Create and open the file using a text editor.

#### **Mac/Linux:**
```sh
nano environment.yml
```

#### **Windows (PowerShell or Command Prompt):**
```sh
notepad environment.yml
```

### **Add the Following Content to the File**
```yaml
name: urban-data-analysis
dependencies:
  - python=3.12
  - ipykernel
  - jupyter
  - pandas
  - matplotlib
  - openpyxl
  - "altair>=5"
  - seaborn
  - statsmodels
  - geopandas
  - tqdm
  - requests
```

- `name: urban-data-analysis` → The environment name.
- `dependencies:` → List of required packages.

**Save and close the file.**

---

## **📌 4. Create the Conda Environment**
Now, use the **environment.yml** file to create the environment.

Run:

```sh
conda env create -f environment.yml
```

This process:
- Creates an environment named **`urban-data-analysis`**.
- Installs Python 3.12 and all required libraries.

---

## **📌 5. Verify the Environment Exists**
After creation, list all Conda environments:

```sh
conda env list
```

or

```sh
conda info --envs
```

Expected output (your path may vary):

```
# conda environments:
#
base                  *  /Users/your-username/anaconda3
urban-data-analysis      /Users/your-username/anaconda3/envs/urban-data-analysis
```

If the environment **does not appear**, recreate it using:

```sh
conda env create -f environment.yml
```

---

## **📌 6. Activate the Environment**
Now, activate the environment to use it:

### **Mac/Linux:**
```sh
conda activate urban-data-analysis
```

### **Windows:**
```sh
conda activate urban-data-analysis
```

If activation fails, try:

```sh
source activate urban-data-analysis
```

To confirm activation, check the Python version:

```sh
python --version
```

Expected output:

```
Python 3.12.x
```

---

## **📌 7. Add the Conda Environment to Jupyter**
To use this environment in **Jupyter Notebook**, register it as a kernel:

```sh
python -m ipykernel install --user --name urban-data-analysis --display-name "Python (urban-data-analysis)"
```

This ensures that Jupyter recognizes the new environment.

---

## **📌 8. Launch Jupyter Notebook**
Now, start Jupyter Notebook:

```sh
jupyter notebook
```

This will open Jupyter in your browser.  
When creating a new notebook, select:

**Kernel → Change Kernel → Python (urban-data-analysis)**

---

## **📌 9. Setting Up Jupyter in VS Code**
To use Jupyter notebooks inside **VS Code**:

1. Open **VS Code**.
2. Press `Ctrl+Shift+P` (`Cmd+Shift+P` on Mac).
3. Search for **"Python: Select Interpreter"** and choose **urban-data-analysis**.
4. Install the **Jupyter** extension from the Extensions Marketplace (`Ctrl+Shift+X`).
5. Open a `.ipynb` file and select **"Python (urban-data-analysis)"** as the kernel.

---

## **📌 10. Running Code in a Jupyter Notebook (VS Code)**
Now, open a **new notebook (`.ipynb`)** and try running the following:

### **Import Required Libraries**
```python
import pandas as pd
import matplotlib.pyplot as plt
import seaborn as sns
import geopandas as gpd
```

### **Load and Display Sample Data**
```python
df = pd.DataFrame({
    "Category": ["A", "B", "C", "D"],
    "Values": [10, 20, 30, 40]
})

df
```

### **Plot a Graph**
```python
plt.figure(figsize=(6,4))
sns.barplot(x="Category", y="Values", data=df)
plt.title("Sample Bar Chart")
plt.show()
```

---

## **📌 11. Updating the Environment**
If you modify `environment.yml` (e.g., adding new libraries), update the environment with:

```sh
conda env update -f environment.yml
```

---

## **📌 12. Deactivating the Environment**
When finished, deactivate the Conda environment:

```sh
conda deactivate
```

---

## **📌 13. Removing the Environment (If Needed)**
If you no longer need this environment, remove it:

```sh
conda env remove --name urban-data-analysis
```

---

## **✅ Summary of Commands**
| **Step** | **Command (Run in Terminal)** |
|----------|--------------------------------|
| Check Conda Installation | `conda --version` |
| Create `environment.yml` | `nano environment.yml` (Mac) / `notepad environment.yml` (Windows) |
| Create Conda Environment | `conda env create -f environment.yml` |
| Verify Environment Exists | `conda env list` |
| Activate Environment | `conda activate urban-data-analysis` |
| Add Kernel to Jupyter | `python -m ipykernel install --user --name urban-data-analysis --display-name "Python (urban-data-analysis)"` |
| Launch Jupyter Notebook | `jupyter notebook` |
| Update Environment | `conda env update -f environment.yml` |
| Deactivate Environment | `conda deactivate` |
| Remove Environment | `conda env remove --name urban-data-analysis` |

---

## **🚀 Now You're Ready!**
Your **`urban-data-analysis`** environment is fully set up and working in **Jupyter Notebook and VS Code**. 🎉




