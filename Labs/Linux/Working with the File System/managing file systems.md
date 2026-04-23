**[MANAGING FILE SYSTEMS]{.underline}**

**USING SSH TO CONNECT TO AN AMAZON LINUX EC2 INSTANCE**

1.  Select the **Download PPK** button and save the **labsuser.ppk**
    file.

2.  Make a note of the **PublicIP** address.

3.  Download **PuTTY** to SSH into the Amazon EC2 instance.

4.  Open **putty.exe** and configure your PuTTY session by following the
    directions in the link provided

**Task 1: Create a Folder Structure**

In this task, I created a specific folder structure. A picture of the
files and folders is provided, and my task is to recreate the structure
in the new machine.

1.  To validate that I am in the home folder of my current user, I
    entered ***pwd*** and pressed enter. If I was not in the home
    folder, I had to enter ***cd /home/ec2-user***

2.  In the terminal, I had to enter ***mkdir CompanyA*** and pressed
    enter to create the top-level folder.

3.  To change directories, I had to enter ***cd CompanyA*** and pressed
    enter.

4.  To create all the sub folders, I had to enter ***mkdir Finance HR
    Management*** and pressed enter.

5.  To validate that the folders were created, I had entered ***ls***
    and pressed enter.

6.  I then wanted to change my current directory to the **HR**
    directory, I had to enter ***cd HR*** and press enter.

7.  To create the empty files inside the **HR** folder, I had to enter
    ***touch Assessments.csv TrialPeriod.csv*** and pressed enter.

8.  To validate that the files were created, I had to enter ***ls*** and
    pressed enter.

9.  To change my current directory to **Finance**, I had to enter ***cd
    ../Finance*** and pressed enter.

10. To create the empty files inside the **Finance** folder, I had to
    enter ***touch Salary.csv ProfitAndLossStatements.csv*** and pressed
    enter.

11. To validate that the files were created, enter **ls** and pressed
    enter.

12. To change directories back one level to the **CompanyA** folder, I
    had to enter ***cd ..*** and pressed enter.

13. To create the new empty files in the **Management** folder, I had to
    enter ***touch Management/Managers.csv Management/Schedule.csv***
    and pressed enter.

14. To validate that the files were created, I had to enter ***ls***
    ***Management*** and pressed enter.

15. To validate that all the files and folders from the **CompanyA**
    folder down had been created, I had to enter ***ls -laR*** and
    pressed enter.

**Task 2: Delete and reorganize folders**

I was later tasked with reorganizing the content

For this task, I:

-   Had to copy the **Finance** folder and its content to the **HR**
    folder, and remove the previous **Finance** folder

-   Move the **Management** folder inside the **HR** folder

-   Create an **Employees** folder inside the **HR** folder, and move
    the **Assessments.csv** and **TrialPeriod.csv** file inside the
    **Employees** folder

1.  To ensure that I am in the appropriate **CompanyA** folder, I had to
    enter ***pwd*** into the terminal and pressed enter.

2.  To copy the **Finance** folder and its content, I had to enter ***cp
    -r Finance HR*** and pressed enter.

3.  To verify that the folder and the content was copied, enter ***ls
    HR/Finance*** and pressed enter.

4.  To remove the **Finance** folder from the **CompanyA** folder
    structure, I had to enter ***rmdir Finance*** and pressed enter.

-   ***rmdir** works only on an empty directory. To remove the folder, I
    had two options:*

```{=html}
<!-- -->
```
-   *I had to remove the files inside the folder and then remove the
    **Finance** folder or,*

-   *Use the **rm** command with the **-r** option to recursively delete
    the folder and its content*

5.  To remove the files inside the **Finance** folder, I had to enter
    ***rm Finance/ProfitAndLossStatements.csv Finance/Salary.csv*** and
    pressed enter.

6.  To verify that the folder is empty, enter ***ls Finance*** and
    pressed enter.

7.  To remove the folder, I had to enter ***rmdir Finance*** and pressed
    enter.

8.  To verify that the folder was removed, enter ***ls*** and pressed
    enter.

9.  To move the **Management** folder inside the **HR** folder, I had to
    enter mv ***Management HR*** and pressed enter.

10. To verify that the folder and files were moved, enter ***ls .
    HR/Management*** and pressed enter.

11. To navigate inside the **HR** folder, I hadd to enter ***cd HR***
    and pressed enter.

12. To create the **Employees** folder, enter ***mkdir Employees*** and
    pressed enter.

13. To move the files to this folder, enter ***mv Assessments.csv
    TrialPeriod.csv Employees*** and pressed enter.

14. To verify that the files were moved, enter ***ls . Employees*** and
    pressed enter.
