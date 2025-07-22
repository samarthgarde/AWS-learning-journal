## 1.Create an S3 bucket:
![Screenshot](./images/oop_beta.png)

+ Go to S3 → Create bucket
+ Bucket name: your-unique-portfolio-name
+ Uncheck✅ “Block all public access”
+ Click Create bucket.

## 2.Upload the  object like image/pdf/ppt

then upoad the index.html file
[Open index.html](./index.html)

## 3.Go to S3 → Your Bucket → Properties

+ Scroll to Static Website Hosting
+ Enable it, and set:
+ Index document: index.html
(Optional) Error document: error.html
![Screenshot](./images/Screenshot (62).png)
  + Save
![Scrrenshot](/images/Screenshot (63).png)

## 4 then going to the object ownership permission

+ enable ACL
+ Object ownership
+ then Save it
![Scrrenshot](/images/Screenshot (64).png)

## 5.then going to the object of our input index.html file 
+ then go to the ACL and check the right permissionon everyone public accesss and check "I undestand"
+ saved it
![Scrrenshot](/images/Screenshot (65).png)

## 6.RUN the url endpoint
![screenshot](images/screenshot (66).png)

✅ You're Done!
