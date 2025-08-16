### Step 1: Setup
**[Datasets](https://github.com/Gooner-Jones/SQL-Data-Warehouse-Project/tree/main/datasets) : ** Access to the project dataset (csv files).

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
   - Use **[Bronze Notebook](https://github.com/Gooner-Jones/Microsoft-Fabric-ZedaFleet-Analysis-Project/blob/main/Notebooks/Bronze%20Notebook.ipynb)**
3. **Save the Data**
    - The file path can be obtained by clicking the three dots next to the **Files** folder in the Lakehouse and selecting **Copy Relative Path** for Spark.
    - Refresh the Lakehouse to see the newly created file.
4. **Load Data into a Dataframe**
    - Click on the file and load it into a DataFrame to verify the data.

### Step 3: Silver Layer Transformation (CSV to Table)

1. **Create a New PySpark Notebook**
2. **Transform Data into a Table**
    - Use **[Silver Notebook](https://github.com/Gooner-Jones/Microsoft-Fabric-ZedaFleet-Analysis-Project/blob/main/Notebooks/Silver%20Notebook.ipynb)**
3. **Write the Data to the Silver Table**
    - Use **overwrite** mode.
    - Refresh the tables to see the new Silver layer.
  
### Step 5: Gold Layer Transformation

1. **Create a New PySpark Notebook**
2. **Transform Data into a Table**
    - Use **[Gold Notebook](https://github.com/Gooner-Jones/Microsoft-Fabric-ZedaFleet-Analysis-Project/blob/main/Notebooks/Gold%20Notebook.ipynb)**
3. **Write the Data to the Silver Table**
    - Use **overwrite** mode.
    - Refresh the tables to see the new Gold layer.
      
### Step 6: Set Up Automated Data Factory Pipeline

1. **Create a Data Pipeline:**
    - Click **Data Factory** > **Data Pipeline**.
    - Enter a name and click **Create**.
2. **Configure Bronze Pipeline Activity:**
    - Click on **Pipeline Activity** > **Notebook**.
    - Name it **Bronze**.
3. **Link Activities:**
    - Go to **Activities** > **Notebook**.
    - Click the green tick to link it from **Bronze**.
4. **Create Silver Notebook:**
    - Name it **Silver**.
    - Go to **Settings** and change the notebook to **Silver**.
5. **Create Gold Notebook:**
    - Add a **Gold Notebook** that runs on the success of **Silver** (link using the tick).
    - Name it **Gold**.
6. **Validate and Run Pipeline:**
    - Click **Validate** > **Run**.
7. **Monitor the Output:**
    - Watch the **Output** for pipeline results.
8. **Monitor Runs:**
    - Check the **Run History** or go to the **Monitoring Hub** to view the pipeline runs.
