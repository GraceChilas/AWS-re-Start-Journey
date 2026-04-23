# DynamoDB Lab

## Task 1: Create a New Table

In this task, I created a new table named **Music** in DynamoDB. Each table required a partition key (primary key) to partition data across DynamoDB servers. A table could also have a sort key, and the combination of both uniquely identified each item.

1. I opened the AWS Management Console and chose **Services**.
2. Under **Database**, I selected **DynamoDB**.
3. I chose **Create table**.
4. For the table name, I entered `Music`.
5. For the partition key, I entered `Artist` and left it as **String**.
6. For the sort key, I entered `Song` and left it as **String**.
7. I used the default settings for indexes and provisioned capacity.
8. I scrolled down and chose **Create table**.

The table was created in less than a minute. I waited until the **Music** table status became **Active** before proceeding.

## Task 2: Add Data

In this task, I added data to the **Music** table.

A table is a collection of items, where each item consists of attributes. Items are similar to rows, and attributes are similar to columns. DynamoDB does not require a fixed schema, so each item can have different attributes.

### First Item

1. I selected the **Music** table.
2. I chose **Actions → Create item**.
3. I entered the following required attributes:
   - Artist: Pink Floyd
   - Song: Money

4. I added additional attributes:
   - Album: The Dark Side of the Moon (String)
   - Year: 1973 (Number)

5. I chose **Create item**.

### Second Item

| Attribute Name | Type   | Value        |
|---------------|--------|--------------|
| Artist        | String | John Lennon  |
| Song          | String | Imagine      |
| Album         | String | Imagine      |
| Year          | Number | 1971         |
| Genre         | String | Soft rock    |

### Third Item

| Attribute Name | Type   | Value                          |
|---------------|--------|--------------------------------|
| Artist        | String | Psy                            |
| Song          | String | Gangnam Style                  |
| Album         | String | Psy 6 (Six Rules), Part 1      |
| Year          | Number | 2011                           |
| LengthSeconds | Number | 219                            |

## Task 3: Modify an Existing Item

1. I navigated to the DynamoDB dashboard.
2. Under **Tables**, I chose **Explore Items**.
3. I selected the **Music** table.
4. I chose the item with Artist **Psy**.
5. I updated the **Year** from `2011` to `2012`.
6. I chose **Save changes**.

## Task 4: Query the Table

### Query Operation

1. I expanded **Scan/Query items** and selected **Query**.
2. I entered:
   - Artist: Psy
   - Song: Gangnam Style
3. I chose **Run**.

### Scan Operation

1. I selected **Scan**.
2. I expanded **Filters** and entered:
   - Attribute: Year
   - Type: Number
   - Value: 1971
3. I chose **Run**.

## Task 5: Delete the Table

1. In the DynamoDB dashboard, I chose **Update settings**.
2. I selected the **Music** table.
3. I chose **Actions → Delete table**.
4. I confirmed by typing `delete` and selecting **Delete table**.

## Conclusion

I successfully:

- Created an Amazon DynamoDB table  
- Added data to the table  
- Queried data using both Query and Scan  
- Updated an existing item  
- Deleted the DynamoDB table  
