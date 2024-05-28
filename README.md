# Project 6 - Data Analytics with Hadoop

## Overview

This project focuses on leveraging Hadoop for data analytics, continuing from the batch processing work done in Project 3. You will create a data mart and use MapReduce to generate monthly order reports.

## Tools

- **Postgres** (via Docker or direct install)
- **Hadoop** (version < 3.2.1)
- **Script Project 3** - Batch Processing
- **GUI for Postgres** (Pgadmin, Dbeaver, etc.) - Optional

## Preparation

1. **Download Batch Processing Script:**
   - [Link to Batch Processing Script](https://github.com/MSinggihP/digitaskola_de_10_batch_processing)

2. **Understand the Script:**
   - Review the script from the previous project (tutors will assist in explaining).

3. **Install Hadoop:**
   - Should already be installed in the Hadoop session.
   - Installation tutorials:
     - [Install Hadoop on Debian 11](https://www.rosehosting.com/blog/how-to-install-hadoop-on-debian-11/) for Ubuntu.
     - [Install Hadoop on Windows 10](https://towardsdatascience.com/installing-hadoop-3-2-1-single-node-cluster-on-windows-10-ac258dd48aef).
     - [Hadoop on Docker](https://medium.com/analytics-vidhya/hadoop-single-node-cluster-on-docker-e88c3d09a256).

4. **Run Hadoop on Docker:**
   ```bash
   docker run -d -it --name hadoop-local -p 9864:9864 -p 9870:9870 -p 8088:8088 --hostname hadoop-local hadoop
   ```

5. **Add Hosts:**
   - Update hosts file:
     ```plaintext
     127.0.0.1 hadoop-local
     35.222.31.142 hadoop-server
     ```
   - Tutorial for Windows: [Custom Domain Name for Localhost](https://ecompile.io/blog/localhost-custom-domain-name)

6. **Ensure Hadoop Services are Running:**
   - Hadoop Namenode
   - Hadoop Datanode
   - YARN Resource Manager
   - YARN Node Manager

7. **Optional:**
   - Connect PostgreSQL database with a GUI of your choice.

## Project Flow

- [Project Flow Diagram](https://drive.google.com/file/d/1rzhm4n4sy4_668xCfLXOlJKhUkj0HV2j/view?usp=sharing)

## Study Case

In the previous project, you created batch processing for data migration. Now, you need to create a data mart table for monthly order reports. This process should take no longer than one hour.

**Requirement:**
- Data mart table with columns: `month`, `total_orders`

## Tasks

1. **Extract Data Source to PostgreSQL:**
   - Skip this step, already completed in Project 3.

2. **Create DWH `dim_orders` Table Using Hadoop:**
   - Define the data warehouse structure in PostgreSQL.

3. **Create Data Mart `total_orders_based_on_month` with MapReduce:**
   - Extract data from the data warehouse using MapReduce.

## Step-by-Step Guide

### ETL Flow Diagram

1. **Create ETL Flow Diagram:**
   - Define the flow of data from extraction to transformation and loading.

2. **Add Hadoop Connection:**
   - Update `config.json` with Hadoop connection details.

### Script Details

1. **Create Connection Scripts:**
   - Define scripts to connect to Hadoop, PostgreSQL, and manage configurations.

2. **Define Datetime Now:**
   - Capture the current datetime for logging and process tracking.

3. **Prepare Dummy Data for DWH:**
   - Generate dummy data locally.

4. **Upload Data to Hadoop:**
   - Use scripts to upload the dummy data to Hadoop, simulating the DWH.

5. **Transform Data with MapReduce:**
   - Implement MapReduce scripts to process the data and generate the required output.

### Project Structure

```plaintext
project-6/
│
├── query/
│   └── dwh_design.sql
│   └── query.sql
├── app.py
├── config.json
├── connection.py
├── requirements.txt
```

## Conclusion

By following these steps and utilizing the provided scripts, you will set up a data analytics project with Hadoop and PostgreSQL, creating a data mart for monthly order reports using MapReduce. This project builds on your previous batch processing work and enhances your skills in big data processing and analytics.

## Contributions

Contributions in the form of pull requests are highly welcome. Please open an issue for further discussion.

## License

Programmed with ❤️ by Gustian.
