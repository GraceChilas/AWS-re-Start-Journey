# AWS IAM Lab – User Management & Permissions

## Overview
In this lab, I worked with AWS Identity and Access Management (IAM) to:
- Strengthen account security using a custom password policy
- Explore users and user groups
- Assign permissions via groups
- Test access control across AWS services

---

## Task 1: Create an Account Password Policy

In this task, I created a custom password policy for my AWS account.

I first noted the Region displayed in the top-right corner of the console.

I then:
- Navigated to the **IAM Console**
- Selected **Account settings**
- Reviewed the default password policy

Since stricter security was required, I:
- Chose **Change password policy**
- Set the minimum password length to **10 characters**
- Selected all checkboxes except:
  - *Password expiration requires administrator reset*
- Kept:
  - Password expiration at **90 days**
  - Password reuse prevention at **5 passwords**

Finally, I saved the changes.

### Summary
I strengthened account security by enforcing stricter password requirements, making user passwords more difficult to compromise.

---

## Task 2: Explore Users and User Groups

In this task, I explored existing IAM users and groups.

### Users
I navigated to **Users** and reviewed:
- user-1
- user-2
- user-3

For **user-1**, I observed:
- No permissions assigned
- Not part of any group
- A console password was configured

### User Groups
I then navigated to **User groups** and reviewed:
- EC2-Admin
- EC2-Support
- S3-Support

#### EC2-Support Group
- Had the **AmazonEC2ReadOnlyAccess** managed policy
- Allowed viewing EC2-related resources but no modifications

#### S3-Support Group
- Had the **AmazonS3ReadOnlyAccess** policy
- Allowed listing and viewing S3 resources

#### EC2-Admin Group
- Used an **inline policy**
- Allowed:
  - Viewing EC2 instances
  - Starting and stopping instances

### IAM Policy Structure
I learned that policies include:
- **Effect**: अनुमति (Allow/Deny)
- **Action**: API operations (e.g., `DescribeInstances`)
- **Resource**: Scope (specific resource or all `*`)

### Summary
I explored IAM users and groups and understood how permissions are applied using managed and inline policies.

---

## Business Scenario

I aligned users with job roles:

| User   | Group        | Permissions                          |
|--------|-------------|--------------------------------------|
| user-1 | S3-Support  | Read-only access to S3              |
| user-2 | EC2-Support | Read-only access to EC2             |
| user-3 | EC2-Admin   | View, start, stop EC2 instances     |

---

## Task 3: Add Users to User Groups

### Add user-1 to S3-Support
I:
- Opened **User groups**
- Selected **S3-Support**
- Added **user-1**

### Add user-2 to EC2-Support
I added **user-2** to the **EC2-Support** group.

### Add user-3 to EC2-Admin
I added **user-3** to the **EC2-Admin** group.

I verified that each group showed **1 user assigned**.

### Summary
I successfully assigned users to groups so they inherited the correct permissions.

---

## Task 4: Sign In and Test Permissions

### Step 1: Access IAM Sign-In URL
I:
- Retrieved the IAM sign-in URL
- Opened it in a private browser window

---

### Test: user-1 (S3 Support)

I signed in as **user-1**.

**Results:**
- ✅ Could view S3 buckets and contents
- ❌ Could NOT access EC2 (unauthorized)

---

### Test: user-2 (EC2 Support)

I signed out and signed in as **user-2**.

**Results:**
- ✅ Could view EC2 instances
- ❌ Could NOT stop instances (read-only restriction)
- ❌ Could NOT access S3

---

### Test: user-3 (EC2 Admin)

I signed out and signed in as **user-3**.

**Results:**
- ✅ Could view EC2 instances
- ✅ Could stop EC2 instances successfully

---

### Summary
I validated that permissions worked as expected:
- user-1 → S3 only
- user-2 → EC2 read-only
- user-3 → Full EC2 admin capabilities

---

## Conclusion

In this lab, I successfully:

- Created and applied an IAM password policy
- Explored IAM users and user groups
- Analyzed managed and inline policies
- Assigned users to appropriate groups
- Tested real-world access control scenarios
