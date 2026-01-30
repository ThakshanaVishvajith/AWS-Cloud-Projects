<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-host-a-website-on-s3)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project, I will demonstrate how to use aws S3 bucket for host a static website I'm doing this project to learn aws cloud services and how they can be use to store objects in the cloud and even host a websites.

### Tools and concepts

Services I used were Amazon S3 Key concepts I learned include bucket policies and hosting a static website, bucket endpoint URLs, access controller lists, and bucket objects.

### Time, challenges, and wins

This project took me approximately one and half hours The most challenging part was resolving the 403 forbidden error. It was most rewarding to see the webpage load live and available on the internet.

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step, I will open S3 because I want to create a storage space inside S3 to store website files.

### How long it took to create the bucket

Creating an S3 bucket took me less than 5 minutes to configure. It takes time to learn about a few concepts that are important for creating an S3 bucket, like ACLs, blocking public access, and bucket versioning.

### Region selection

The region I picked for my S3 bucket was Mumbai because it is the region closest to me. it's a best practice to select a closes region because it reduces the latency and cost when retrieving things in the S3 bucket

### Understanding bucket name uniqueness

S3 bucket names are globally unique! This means no two Amazon S3 buckets can have the same name. They have to be completely unique regardless of the region  and the account ID. 

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I will upload the website files to the S3 bucket  because the S3 bucket want to have the files of the website to host it on the aws S3

### Files I uploaded

I uploaded two files to my S3 bucket: index.html, which provide the structure of the website and other files that provide the content of the website

### How the files work together

Both files are necessary for this project, as the index.html gives the structure but does not include the content. The index.html says the image wants to place itself there, and the image is contained in other files.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I will make the website available on the internet because the files remain just files, not a website if we do not make it available over internet

### Understanding website hosting

Website hosting means putting the website files on the server, which make the website files publicly available over the internet

### How I enabled website hosting

To enable website hosting with my S3 bucket, I go to the properties tab and enable static web hosting and labeled the index.html as the index document.

### Access Control Lists (ACLs)

An ACL is an access control list. It is a way to configure permission settings inside a bucket. We enable ACLs so we can control access to our website files later. keep enabling ACLs to learn how it works and compare it with bucket policies later

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once a static website is enabled, S3 produces a bucket endpoint URL, which is a URL that takes anyone on the internet to the website that we are hosting.

### What I saw when I tested the endpoint

When I first visited the bucket endpoint URL, I saw a 403 Forbidden error. The reason for this error was the objects in the S3 bucket are private by default even we switche off "block public access" the website files themselves are completel private.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

In this step, I will go into the files that we uploaded into our bucket and make them public too because this will enable us to actually view the content of our website.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I updated the access settings of the files inside the S3 bucket to use ACLs to make the bucket files public. Once I check the bucket endpoint after updating ACLs, the website is available.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

### Understanding bucket policies

### What my bucket policy does

---

---
