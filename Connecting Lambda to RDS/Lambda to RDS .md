**Connecting AWS Lambda to Amazon RDS**

1. **I Created the RDS Instance**

   * I used the *Standard Create* option and selected the MySQL engine on the free tier (db.t3.micro, 20 GB gp2 storage).
   * I enabled public access and assigned a security group (e.g., `DB-SG`) that allows inbound traffic on port **3306**.

2. **I Noted Down the Connection Details**

   * After the RDS instance was ready, I copied the DB endpoint, username, and password. I used these later in my Lambda configuration.

3. **I Created the Lambda Function**

   * I authored the function from scratch using **Python 3.12** and attached a pre-existing IAM role with the required permissions.

4. **I Configured VPC & Security Groups for Lambda**

   * I attached the same VPC and subnets that my RDS instance uses.
   * I added the `DB-SG` security group to my Lambda function’s network settings.
   * I also made sure `DB-SG` allowed inbound traffic from Lambda on port **3306**.

5. **I Uploaded and Checked the Lambda Code**

   * I uploaded the provided `.zip` file, which included a Python script using `pymysql`.
   * The script read DB credentials from environment variables and executed `SHOW DATABASES;`.
   * It returned HTTP 200 if successful, 404 if nothing was found, or 500 on errors.
   * The DB connection was properly closed after execution.

6. **I Set Environment Variables**

   * In the Lambda console, under Configuration → Environment variables, I added:

     ```
     DB_HOST = <RDS endpoint>
     DB_USER = <username>
     DB_PASSWORD = <password>
     DB_NAME = mysql
     ```
   * I also increased the function timeout to around 1 minute.

7. **I Linked Lambda to RDS**

   * In the RDS Console, I used the **“Set up Lambda connection”** option to link my function (without using RDS Proxy).
   * I waited for both Lambda and RDS to finish the connection setup.

8. **I Tested the Lambda Function**

   * I created a test event with a basic JSON payload.
   * When I ran the function, I checked the logs and status code to confirm that it successfully connected to the database and ran the SQL query.

---

