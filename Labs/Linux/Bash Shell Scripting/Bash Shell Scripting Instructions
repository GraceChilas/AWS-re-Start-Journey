
# EC2 & Linux Commands

## Connecting to EC2 Using PuTTY

1. I select the **Download PPK** button and save the `labsuser.ppk` file. 

2. I make a note of the **Public IP address**.  

3. I download **PuTTY** so I can SSH into my Amazon EC2 instance.  

4. I configure my PuTTY session by following the directions provided in the guide to connect to my Linux instance using PuTTY.  


---

## Creating a Backup Alias

Specifically, I create an alias that gives me the ability to back up whatever path I provide.

1. To validate that I am in the home folder, I enter:
   ```bash
   pwd
````

2. To create an alias called `backup`, I enter:

   ```bash
   alias backup='tar -cvzf '
   ```

3. To back up the `CompanyA` folder, I enter:

   ```bash
   backup backup_companyA.tar.gz CompanyA
   ```

4. To verify that the archive is created, I enter:

   ```bash
   ls
   ```

---

## Explore and Update the PATH Environment Variable

In this task, I display the PATH environment variable, update it, and add a new directory for executables.

1. To navigate to the `bin` folder:

   ```bash
   cd /home/ec2-user/CompanyA/bin
   ```

2. I can verify my location using:

   ```bash
   pwd
   ```

   Then navigate using:

   ```bash
   cd CompanyA/bin
   ```

3. To run the script:

   ```bash
   ./hello.sh
   ```

4. To go to the parent directory:

   ```bash
   cd ..
   ```

5. To run the script again:

   ```bash
   ./bin/hello.sh
   ```

6. I attempt to run the script directly:

   ```bash
   hello.sh
   ```

7. I analyze why this method fails and investigate further.

8. To display the PATH variable:

   ```bash
   echo $PATH
   ```

9. I navigate back and run:

   ```bash
   cd /home/ec2-user/CompanyA/bin
   hello.sh
   ```

10. I can also run it from anywhere using:

    ```bash
    /home/ec2-user/CompanyA/bin/hello.sh
    ```

11. To add the directory to PATH:

    ```bash
    PATH=$PATH:/home/ec2-user/CompanyA/bin
    ```

12. I test it again:

    ```bash
    hello.sh
    ```

```
