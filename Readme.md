# Conda Environment Setup 🚀

`environment.yml` files in **conda** are powerful! Here’s a **comprehensive list** of what you can do with them, explained briefly:

---

## 🔹 Core Functions

1. **Create environments**

   ```bash
   conda env create -f environment.yml
   ```

   Reproduces the exact environment described in the YAML.

2. **Update environments**

   ```bash
   conda env update -f environment.yml --prune
   ```

   Syncs your environment with the YAML (adding/removing packages).

3. **Share environments**
   Export your current env:

   ```bash
   conda env export > environment.yml
   ```

   Share with collaborators to ensure reproducibility.

---

## 🔹 What You Can Specify Inside `environment.yml`

1. **Environment name**

   ```yaml
   name: myenv
   ```

2. **Channels (priority sources)**

   ```yaml
   channels:
     - conda-forge
     - defaults
   ```

   Defines where to fetch packages from (order = priority).

3. **Dependencies with versions**

   ```yaml
   dependencies:
     - python=3.10
     - numpy=1.24
   ```

   You can pin versions for consistency.

4. **Groups of dependencies** (default vs optional)

   ```yaml
   dependencies:
     - pandas
     - pip:
       - flask
   ```

   Conda deps vs pip-only deps.

5. **Nested dependencies (pip integration)**
   Lets you mix conda + pip packages in one file.

6. **Platform-specific packages** (via selectors, if using conda-build)
   Example:

   ```yaml
   - python=3.10  # [linux]
   - python=3.11  # [win]
   ```

7. **Exact builds (for strict reproducibility)**
   You can lock down to build numbers:

   ```yaml
   - pytorch=2.1.2=py3.10_cuda11.8_cudnn8.7
   ```
