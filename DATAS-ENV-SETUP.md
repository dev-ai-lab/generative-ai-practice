**Intel MacBook ML + GenAI Setup (Python 3.13, Miniconda + VS Code & IntelliJ)**

---

**1️⃣ Remove old Python.org installation (optional but recommended)**

```bash
sudo rm -rf /Library/Frameworks/Python.framework/Versions/3.12
sudo rm -f /usr/local/bin/python3
sudo rm -f /usr/local/bin/pip3
```

> Cleans up old Python to avoid conflicts.

---

**2️⃣ Install Miniconda (Intel macOS)**

```bash
curl -LO https://repo.anaconda.com/miniconda/Miniconda3-latest-MacOSX-x86_64.sh
bash Miniconda3-latest-MacOSX-x86_64.sh -b -p $HOME/miniconda3
rm Miniconda3-latest-MacOSX-x86_64.sh
```

---

**3️⃣ Initialize Conda for zsh**

```bash
$HOME/miniconda3/bin/conda init zsh
source ~/.zshrc
```

✅ After this, `conda activate` works.

---

**4️⃣ Verify Conda**

```bash
conda --version
```

Expected output: `conda 23.x.x`

---

**5️⃣ Create ML / GenAI environment (Python 3.13)**

```bash
conda create -n genai python=3.11 -y # We select python 3.11 and not 3.13 as tensorflow needs 3.11 or lower
conda activate genai
```

✅ You should see `(genai)` in your prompt.

---

**6️⃣ Install ML / Data Science / LLM packages**
Alway active the environment before install a new package or library.
Search the package in [here](https://anaconda.org/), and then install the package as suggested.

```bash
# Data science basics
conda install -c conda-forge numpy pandas scipy matplotlib seaborn scikit-learn jupyterlab ipykernel -y

# In case the env is broken, then
conda install -c conda-forge --force-reinstall numpy scipy pandas matplotlib seaborn scikit-learn -y

# PyTorch CPU-only (Intel Mac)
conda install pytorch torchvision torchaudio cpuonly -c pytorch -y
conda install pytorch torchvision torchaudio -c conda-forge  -y

# Tensor flow
conda install conda-forge::tensorflow

# Hugging Face / LLM packages
pip install transformers datasets accelerate evaluate
pip install langchain openai sentence-transformers
```


Note: If some additional environment is activated in addition to genai (except base), then do: 

```bash
deactivate
# Then
conda activate genai

```

**Conda commands reference**
```bash
conda remove tensorflow

```
---

**Issue with tensor flow**

```bash
# 1. Remove broken environment
conda deactivate
conda env remove -n genai

# 2. Create clean environment using conda-forge
conda create -n genai python=3.11 -c conda-forge -y
conda activate genai

# 3. Install scientific Python stack from conda-forge
conda install -c conda-forge \
numpy scipy pandas matplotlib seaborn jupyter ipykernel -y

# 4. Downgrade NumPy to TensorFlow-compatible version
pip install numpy==1.26.4

# 5. Install TensorFlow via pip (NOT conda)
pip install tensorflow

```


**7️⃣ VS Code Setup**

1. Install **Python** and **Jupyter** extensions.
2. Press `Cmd+Shift+P` → **Python: Select Interpreter** → choose your `genai` environment.
3. Open `.ipynb` notebooks — they’ll use the selected environment.

---

**8️⃣ IntelliJ IDEA / PyCharm Setup**
1. Preferences → Project → Project SDK → Add → Conda Environment → Existing environment
2. Navigate to:

```text
~/miniconda3/envs/genai/bin/python
```

3. Apply → IntelliJ/PyCharm will now use the same Conda environment.

> Works for scripts, notebooks (PyCharm Professional), and debugging ML/GenAI projects.

---

**9️⃣ Managing Multiple Conda Environments**

| Action                  | Command                                     | Notes                                 |
| ----------------------- | ------------------------------------------- | ------------------------------------- |
| List environments       | `conda env list`                            | Shows `base`, `genai`, `ds`, etc.     |
| Activate env            | `conda activate genai`                      | Only one environment active at a time |
| Deactivate env          | `conda deactivate`                          | Returns to `base`                     |
| Install packages in env | `conda install <pkg>` / `pip install <pkg>` | Packages isolated per environment     |
| Delete environment      | `conda remove -n ds --all`                  | Removes entire env                    |
| Export env              | `conda env export > env.yaml`               | Save environment config               |
| Recreate env            | `conda env create -f env.yaml`              | Reproduce environment elsewhere       |

**💡 Python Cleanup Note**

* Remove all old Python.org versions to avoid conflicts with Conda.
* Check system locations:

    * `/Library/Frameworks/Python.framework/Versions/` → old versions like `3.7`, `3.9`, `3.12`
    * `/usr/local/bin/` → old symlinks (`python3.7`, `pip3.7`, `python3.12`, etc.)
* Delete old versions and symlinks **except** Conda’s binaries in `~/miniconda3/bin/`.
* After cleanup, refresh shell:

```bash
hash -r
```

* Verify Conda Python is default:

```bash
which python
python --version
```

✅ Only Conda Python should remain; this ensures ML/LLM/GenAI projects use the correct environment.


