# Lab Solution: Host a Static Website on Amazon S3

**Student Name:** ________Dennis___________________  
**Date:** _____09,07,26______________________  
**Lab Completion Time:** ____60_______ minutes

---

## Part 1: Bucket Configuration

### Bucket Information

**Bucket Name:** ___my-static-website-db-2026________________________

**Region:** _________us-east-1__________________

**Bucket Website Endpoint URL:**
```
________________http://my-static-website-db-2026.s3-website-us-east-1.amazonaws.com/___________________________________________
```

**Screenshot 1: Bucket Creation Confirmation**
![Bucket Created](screenshots/01-bucket-created.png)

---

## Part 2: Static Website Hosting Configuration

### Configuration Details

**Index Document:** _________x__________________

**Error Document:** ____________x_______________

**Screenshot 2: Static Website Hosting Settings**
![Static Hosting Config](screenshots/02-static-hosting-config.png)

---

## Part 3: Website Files

### Files Created

List the files you created:
1. _____index.html______________________
2. _____styles.css______________________
3. _____error.html______________________

**Did you customize the HTML/CSS?** (Yes/No): __no____

**If yes, describe your customizations:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

**Screenshot 3: Files Uploaded to S3**
![Files in S3](screenshots/03-files-uploaded.png)

---

## Part 4: Bucket Policy

### Bucket Policy Applied

**Paste your complete bucket policy here:**
```json
{
    "Version": "2012-10-17",
    "Statement": [
        {
            "Sid": "PublicReadGetObject",
            "Effect": "Allow",
            "Principal": "*",
            "Action": "s3:GetObject",
            "Resource": "arn:aws:s3:::my-static-website-db-2026/*"
        }
    ]
}
```

**Screenshot 4: Bucket Policy Configuration**
![Bucket Policy](screenshots/04-bucket-policy.png)

---

## Part 5: Testing and Verification

### Website Testing

**Website URL (from endpoint):**
```
_____http://my-static-website-db-2026.s3-website-us-east-1.amazonaws.com/______________________________________________________
```

**Did the website load successfully?** (Yes/No): ____y__

**Did the CSS styling apply correctly?** (Yes/No): ___y___

**Screenshot 5: Working Website**
![Website Live](screenshots/05-website-live.png)

### Error Page Testing

**Test URL used:**
```
____http://my-static-website-db-2026.s3-website-us-east-1.amazonaws.com/nonexistent.html_______________________________________________________
```

**Did custom error page display?** (Yes/No): __y____

**Screenshot 6: Custom 404 Error Page**
![Error Page](screenshots/06-error-page.png)

---

## Part 6: CLI Commands Used

**Document all AWS CLI commands you executed:**

```bash
# Bucket creation
aws s3api create-bucket \
  --bucket my-static-website-db-2026 \
  --region us-east-1

# Enable website hosting
did in console

# Upload files
aws s3 cp index.html s3://my-static-website-db-2026/
aws s3 cp error.html s3://my-static-website-db-2026/
aws s3 cp style.css s3://my-static-website-db-2026/
aws s3 sync ./public s3://my-static-website-db-2026/ --exclude ".git/*"



# Apply bucket policy
aws s3api put-bucket-policy \
  --bucket my-static-website-db-2026 \
  --policy file://bucket-policy.json

# Verify configuration
aws s3api get-bucket-website --bucket my-static-website-db-2026
aws s3api get-bucket-policy --bucket my-static-website-db-2026

```

---

## Bonus Challenges Completed

- [ ] Challenge 1: Added about.html page
- [ ] Challenge 2: Used subdirectories for organization
- [ ] Challenge 3: Used `aws s3 sync` command

**Bonus Challenge Notes:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

---

## Reflection Questions

### 1. What are the advantages of S3 static hosting compared to traditional web servers?

**Your answer:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

### 2. Why is a bucket policy necessary for public website access?

**Your answer:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

### 3. What are the limitations of S3 static website hosting?

**Your answer:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

### 4. When would you NOT use S3 for website hosting?

**Your answer:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

### 5. How does S3 static hosting fit into cost optimization strategies?

**Your answer:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

---

## Troubleshooting Log

**Did you encounter any issues?** (Yes/No): ______

**If yes, document the issues and how you resolved them:**

| Issue | Error Message | Solution | Time to Resolve |
|-------|--------------|----------|-----------------|
|       |              |          |                 |
|       |              |          |                 |
|       |              |          |                 |

---

## Cleanup Confirmation

- [ ] Emptied S3 bucket
- [ ] Deleted S3 bucket
- [ ] Verified no resources remain

**Cleanup CLI commands used:**
```bash
# Empty bucket


# Delete bucket


```

---

## Self-Assessment

**Rate your understanding of each concept (1-5, where 5 is expert):**

| Concept | Rating | Notes |
|---------|--------|-------|
| S3 bucket creation | ___/5 | |
| Static website hosting configuration | ___/5 | |
| Bucket policies and public access | ___/5 | |
| Uploading and managing S3 objects | ___/5 | |
| S3 website endpoints | ___/5 | |
| HTML/CSS basics | ___/5 | |

---

## Instructor Verification

**Instructor Name:** ___________________________

**Date Reviewed:** ___________________________

**Website URL Verified:** ☐ Yes ☐ No

**Comments:**
```
_____________________________________________________________
_____________________________________________________________
_____________________________________________________________
```

**Grade/Status:** ___________________________

---

## Additional Resources Referenced

List any documentation, tutorials, or resources you used:

1. ___________________________________________________________
2. ___________________________________________________________
3. ___________________________________________________________

---

**Lab Status:** ☐ Complete ☐ Needs Revision

**Total Time Spent:** ________ minutes

**Submission Date:** ___________________________
