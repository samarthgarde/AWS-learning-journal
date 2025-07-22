# 📝 Title: Deploy a Static Website on AWS S3 using Console

## 1.Create an S3 bucket:

+ Go to S3 → Create bucket
+ Bucket name: your-unique-portfolio-name
+ Uncheck ✅ “Block all public access”
+ Click Create bucket

![Screenshot](./images/oop_beta.png)

## 2.Upload the  object like image/pdf/ppt

then upoad the index.html file
[Open index.html](./index.html)

## 3.Go to S3 → Your Bucket → Properties

+ Scroll to Static Website Hosting
+ Enable it, and set:
+ Index document: index.html
(Optional) Error document: error.html
+ Save

![Screenshot](./images/jddk_5.png)


## 4.Going to the object ownership permission

+ enable ACL
+ Object ownership
+ then Save it

![Scrrenshot](./images/omg_ok.png)

## 5.Going to the object of our input index.html file 

+ then go to the ACL and check the right permissionon everyone public accesss and check "I undestand"
+ saved it

![Scrrenshot](./images/oop_bet_3.png)


## 6.RUN the url endpoint

![screenshot](./images/oop_betas_1.png)

## 7.Paste in your browser to view your hosted website

![screenshot](./images/ossj_4.png)

✅ You're Done!
