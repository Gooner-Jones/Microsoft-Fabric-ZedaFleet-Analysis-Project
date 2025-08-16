### Step 1: Setup
**[Datasets](datasets/):** Access to the project dataset (csv files).

1. **Create Microsoft Work Email**
2. **Sign In to Fabric**
    - Go to [Microsoft Fabric](https://app.fabric.microsoft.com/) and sign in using your new work email.
3. **Create a Fabric Workspace**
    - Select any experience.
    - On the left panel, click on "Workspaces" and then "New Workspace".
4. **Create a Lakehouse**
    - On the bottom left, navigate to **Data Engineering**.
    - Select **Lakehouse** under Recommended or go to your workspace and click **+ New**.
    - Name your Lakehouse. This will store the data ingested from the API.
    - Note: Delta format is the default table format, optimized for version control and efficient querying.
5. **Lakehouse Overview**
    - You can switch between the **Lakehouse** and **SQL Analytics Endpoint** using the top right options.
    - The Lakehouse is your central data repository, the SQL endpoint provides SQL access, and the semantic model layer helps define business logic.
        - A semantic model is a structured representation of data that defines relationships, meanings, and rules to provide context and support better analysis and             understanding.

### Step 2: Fetch API Data with Python (Bronze Layer)

1. **Create a Notebook in the Lakehouse**
    - Click **+ New** → **Notebook**. Ensure the language is set to **PySpark**.
    - Attach your Lakehouse to the notebook.
2. **Python Code to Fetch Data**
   - Use **[Bronze Notebook](Notebooks/Bronze Notebook.ipynb):** Access to the project dataset (csv files).
