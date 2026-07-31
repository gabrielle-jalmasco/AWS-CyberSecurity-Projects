<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Host a Website on Amazon S3

**Project Link:** [View Project](http://nextwork.ai/projects/aws-host-a-website-on-s3)

**Author:** Gabrielle G. Jalmasco  
**Email:** jalmascogab002@gmail.com

---

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Introducing Today's Project!

### Project overview

In this project we’ll host a static website using Amazon Simple Storage Service (S3). We'll create and configure an S3 bucket to serve the site’s files and to store images and other files.

### Tools and concepts

I used only Amazon S3 for this project. Through the process I learned the purpose and core functions of S3 and how to configure it to manage and host a static website.

### Time, challenges, and wins

The project took about an hour to complete. Some steps were challenging—after uploading and publishing the files I could view only the raw HTML because I had not configured object permissions correctly. I fixed this by updating the bucket permissions, and when the site finally loaded I felt rewarded seeing the finished output.

---

## How I Set Up an S3 Bucket

### What I did in this step

In this step I’ll open the Amazon S3 console and create an S3 bucket to store the website’s files.

### How long it took to create the bucket

Creating an S3 bucket is quick and straightforward; I set one up in under thirty minutes, and in many cases you can have a bucket ready to host your site in just a few minutes.

### Region selection

I selected the default AWS region in the United States.

### Understanding bucket name uniqueness

S3 bucket names must be globally unique, so choose a name that only you use; once created, no one else can create a bucket with the same name.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_ba6d42ad)

---

## Upload Website Files to S3

### What I did in this step

In this step, I downloaded the test files and folders containing the website’s HTML structure and supporting assets, then uploaded them to the S3 bucket.

### Files I uploaded

I uploaded two objects to the S3 bucket: index.html, which contains the site’s main structure, and an assets bundle that holds stylesheets, scripts, images, and other supporting files.

### How the files work together

Both the folder and the file are essential: the HTML file provides the website’s structure, while the folder contains the visuals, images, scripts, and stylesheets that add design and interactivity.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_a265af88)

---

## Static Website Hosting on S3

### What I did in this step

In this step, I configured the S3 bucket for static website hosting by setting the index document and adjusting permissions so the site’s files can be publicly accessed.

### Understanding website hosting

Website hosting means making your site publicly accessible so anyone can view it online.

### How I enabled website hosting

To enable website hosting, I turned on Static Website Hosting in the bucket’s Properties and set index.html as the default document, making the site publicly accessible.

### Access Control Lists (ACLs)

An access control list (ACL) is a set of rules that determines who can access a resource. I enabled ACLs so I can grant specific AWS accounts permission to manage the hosted website when needed.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_c22c54c0)

---

## Bucket Endpoints

### Understanding bucket endpoint URLs

Once static website hosting is enabled, Amazon S3 generates a bucket endpoint URL. This unique link corresponds to the bucket name you created and serves as the public address of your website.

### What I saw when I tested the endpoint

The initial visit showed a 403 error, meaning public access was denied. Adjusting bucket permissions resolved it.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_22ce4daf)

---

## Success!

### What I did in this step

I click the generated S3 website endpoint to verify the site is live after making the bucket objects publicly accessible.

### How I resolved the 403 error

To resolve this 403 Forbidden error, I selected all of the Bucket's content and configured it by making all of the files and folders Public in the ACL settings.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_5d4474f9)

---

## Bucket Policies

### What I did in this extension

In this project extension I'm about to set up a Bucket Policy. I'm doing this so that people stop accidentally deleting my main index.html file.

### Understanding bucket policies

An alternative to ACLs are bucket policies, which allows users to define permissions for an entire bucket and all the objects within. The benefit of using bucket policies is you have the control of who manages or deletes the objects files.

![Image](http://nextwork.ai/genuine_orange_serene_turtle/uploads/aws-host-a-website-on-s3_sm2sm2sm)

### What my bucket policy does

My bucket policy prevents accidental deletion of objects. I verified this by attempting to delete index.html; the console returned an “Access denied” error, confirming the policy is working as intended.

---

---
