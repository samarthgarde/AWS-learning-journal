# 📝 Title: Deploy a Static Website on AWS S3 using Console

## 1.Create an S3 bucket:

+ Go to S3 → Create bucket
+ Bucket name: your-unique-portfolio-name
+ Uncheck ☐ “Block all public access”
+ Click Create bucket

![Screenshot](./images/oop_beta.png)

## 2.Upload the  object like image/pdf/ppt

+ Then upoad the index.html file
[Open index.html](./index.html)

## 3.Go to S3 → Your Bucket → Properties

+ Scroll to Static Website Hosting
+ Enable it, and set:
+ Index document: index.html
+ Error document: error.html (Optional)
+ Save

![Screenshot](./images/jddk_5.png)

## 4. Edit Policy (policy Generator)
- Type of policy - s3 bucket policy
- effect- allow
- principle-*
- action-get object
- ARN-arn:aws:s3:::my-portfolio-host-487527603894
- Add statement
- Generate policy
- Copy the policy to bucket policy and say save changes

## 5.Going to the object ownership permission

+ enable ACL
+ Object ownership
+ then Save it

![Scrrenshot](./images/omg_ok.png)

## 6.Going to the object of our input index.html file 

+ then go to the ACL and check the right permissionon everyone public accesss and check "I undestand"
+ saved it

![Scrrenshot](./images/oop_bet_3.png)


## 6.RUN the url endpoint

![screenshot](./images/oop_betas_1.png)

## 7.Paste in your browser to view your hosted website

![screenshot](./images/ossj_4.png)

✅ You're Done!
