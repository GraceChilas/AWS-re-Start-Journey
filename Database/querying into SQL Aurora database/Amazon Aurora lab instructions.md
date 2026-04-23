# Aurora Database Lab

## Task 1: Create an Aurora Instance

In this task, I created an Aurora database (DB) instance.

1. I opened the AWS Management Console and searched for **RDS**.
2. In the left navigation menu, I chose **Databases**.
3. I selected **Create database** and configured the following:
   - I chose **Standard create**.
   - I selected **Aurora (MySQL Compatible)** as the engine type.
   - I used the default version for MySQL 8.0.
   - I selected the **Dev/Test** template.

4. In the Settings section:
   - I entered `aurora` as the DB cluster identifier.
   - I set the master username to `admin`.
   - I set and confirmed the password as `admin123`.

5. In Instance configuration:
   - I selected **Burstable classes (t class)**.
   - I chose `db.t3.medium`.

6. In Availability & durability:
   - I chose **Don't create an Aurora Replica**.

7. In Connectivity:
   - I selected **LabVPC**.
   - I chose **dbsubnetgroup**.
   - I set **Public access** to **No**.
   - I selected an existing VPC security group.
   - I removed the default group and chose **DBSecurityGroup**.

8. In Monitoring:
   - I disabled Enhanced monitoring.

9. In Additional configuration:
   - I set the initial database name to `world`.

10. In Encryption:
   - I disabled encryption.

11. In Maintenance:
   - I disabled auto minor version upgrades.

12. I created the database and waited for it to become available.

---

## Task 2: Connect to an Amazon EC2 Linux Instance

In this task, I connected to a pre-configured EC2 instance.

1. I searched for **EC2** in the AWS Management Console.
2. I selected **Instances**.
3. I chose the instance labeled **Command Host**.
4. I selected **Connect**.
5. I chose **Session Manager**.
6. I opened the terminal by selecting **Connect**.

---

## Task 3: Configure EC2 to Connect to Aurora

In this task, I installed the MariaDB client and connected to the Aurora instance.

1. I installed the MariaDB client:
```bash
sudo yum install mariadb -y
```

2. I returned to the RDS console and selected my Aurora database.
3. I copied the **Writer endpoint**.

4. I connected to the database using:
```bash
mysql -u admin --password='admin123' -h <endpoint>
```

---

## Task 4: Create a Table and Query Data

In this task, I created a table, inserted records, and queried data.

1. I listed databases:
```sql
SHOW DATABASES;
```

2. I selected the database:
```sql
USE world;
```

3. I created a table:
```sql
CREATE TABLE `country` (
`Code` CHAR(3) NOT NULL DEFAULT '',
`Name` CHAR(52) NOT NULL DEFAULT '',
`Continent` enum('Asia','Europe','North America','Africa','Oceania','Antarctica','South America') NOT NULL DEFAULT 'Asia',
`Region` CHAR(26) NOT NULL DEFAULT '',
`SurfaceArea` FLOAT(10,2) NOT NULL DEFAULT '0.00',
`IndepYear` SMALLINT(6) DEFAULT NULL,
`Population` INT(11) NOT NULL DEFAULT '0',
`LifeExpectancy` FLOAT(3,1) DEFAULT NULL,
`GNP` FLOAT(10,2) DEFAULT NULL,
`GNPOld` FLOAT(10,2) DEFAULT NULL,
`LocalName` CHAR(45) NOT NULL DEFAULT '',
`GovernmentForm` CHAR(45) NOT NULL DEFAULT '',
`Capital` INT(11) DEFAULT NULL,
`Code2` CHAR(2) NOT NULL DEFAULT '',
PRIMARY KEY (`Code`)
);
```

4. I inserted records:
```sql
INSERT INTO `country` VALUES ('GAB','Gabon','Africa','Central Africa',267668.00,1960,1226000,50.1,5493.00,5279.00,'Le Gabon','Republic',902,'GA');
INSERT INTO `country` VALUES ('IRL','Ireland','Europe','British Islands',70273.00,1921,3775100,76.8,75921.00,73132.00,'Ireland/Éire','Republic',1447,'IE');
INSERT INTO `country` VALUES ('THA','Thailand','Asia','Southeast Asia',513115.00,1350,61399000,68.6,116416.00,153907.00,'Prathet Thai','Constitutional Monarchy',3320,'TH');
INSERT INTO `country` VALUES ('CRI','Costa Rica','North America','Central America',51100.00,1821,4023000,75.8,10226.00,9757.00,'Costa Rica','Republic',584,'CR');
INSERT INTO `country` VALUES ('AUS','Australia','Oceania','Australia and New Zealand',7741220.00,1901,18886000,79.8,351182.00,392911.00,'Australia','Constitutional Monarchy, Federation',135,'AU');
```

5. I queried the table:
```sql
SELECT * FROM country WHERE GNP > 35000 AND Population > 10000000;
```

The query returned results for Australia and Thailand.

---

## Conclusion

I successfully:

- Created an Aurora database instance  
- Connected to an EC2 instance  
- Configured EC2 to connect to Aurora  
- Created a table and inserted data  
- Queried the database  
