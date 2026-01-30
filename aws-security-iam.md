<img src="https://cdn.prod.website-files.com/677c400686e724409a5a7409/6790ad949cf622dc8dcd9fe4_nextwork-logo-leather.svg" alt="NextWork" width="300" />

# Cloud Security with AWS IAM

**Project Link:** [View Project](http://learn.nextwork.org/projects/aws-security-iam)

**Author:** muluthukubura@gmail.com  
**Email:** muluthukubura@gmail.com

---

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_1c864649)

---

## Introducing Today's Project!

### Project overview

Launch two EC2 instances and control who has access to them by creating IAM policies to learn about cloud security from absolute foundations.

### Tools and concepts

Services I used Amazon EC2 and AWS IAM for this project. key concept. I learned to include IAM user policies, user groups, and account aliases. I also learn how to use the policy simulator and how JSON policies work, how to launch an instance, how to tag an instance, and how to log in as another user.


### Project reflection

This project took me approximately one and half hours The most challenging part was writing IAM policies in JSON. It was most rewarding to see permission denied when our intern tried to delete our production instance—our IAM access management setup is working.


---

## Tags

### What I did in this step

In this step, I will launch two EC2 instances because we need to boost computing power. We are expecting more users and traffic to the website over the summer.

### Understanding tags

Tags are organizational tools that let us label our resources. In this project. They are helpful for grouping resources, cost allocation, and applying policies for all resources with the same tag.


### My tag configuration

The tag I have used in the EC2 instances is called Env, which stands for Environment. The values I've assigned for instances are production and development.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_2e0e5a5d)

---

## IAM Policies

### What I did in this step

In this step I will use IAM policies to control the access level of a new intern because they should have access to the development environment (i.e., the development instance) but NOT the production environment.

### Understanding IAM policies

IAM policies are the rules that determine who can do what in our AWS account. We're using policies today to control who has access to our production/environment instance.

### The policy I set up

For this project, I’ve set up a policy using JSON by writing  values to Effect  : , Action : , Resource : , Condition : . Ensuring this policy allows some actions (like starting, stopping, and describing EC2 instances) for instances tagged with "Env = development" while denying the ability to create or delete tags for all instances.

### Policy effect

I have created a policy that allows the policyholder (i.e. the interns) to have the permission to do anything they want to any instance tagged with "development."  They can also see information for any instance, but they're denied access to deleting/creating tags for any instance as well.

### Understanding Effect, Action, and Resource

The Effect, Action, and Resources attributes of a JSON policy mean whether or not the policy is allowing/denying action (i.e., Effect) and what the policyholder can or cannot do (i.e., Action): and the specific AWS resources that policy is related to (i.e., resource).

---

## My JSON Policy

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_1c864649)

---

## Account Alias

### What I did in this step

In this step, we will set up an account alias, which is like a nickname for our AWS account's console login. This is because an account alias makes it simpler for our users to log in.


### Understanding account aliases

An account alias is simply a nickname for our AWS account. Instead of a long account ID, we can now reference our account alias instead.


### Setting up my account alias

Creating an account alias took me less than 10 seconds Now, my new AWS console sign-in URL is http://aias-thakshana.signing.aws.amazon.com/console

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_0eb4439b)

---

## IAM Users and User Groups

### What I did in this step

In this step, I will set up two IAM resources—IAM users and IAM user groups. This is because IAM users are like logins for people that want access to our AWS account, while user groups are like folders to manage users that have the same level of access to our AWS resources.


### Understanding user groups

IAM user groups are like folders that collect IAM users so that you can apply permission settings at the group level.

### Attaching policies to user groups

I attach the policy that created to this user group, which means any user created inside this group will automatically get the permissions attached to our DevEnvironment policy IAM policy.


### Understanding IAM users

IAM users are people or entities that have access to/can log in to our AWS account.

---

## Logging in as an IAM User

### Sharing sign-in details

The first way is to email sign-in instructions to the user, while the second way is to download a .csv file with the sign-in details.

### Observations from the IAM user dashboard

Once we logged in as our IAM user, I noticed that our user was already denied access to panels on the main AWS console dashboard. This was because we only set up permission to our development EC2 instance, so our intern wouldn't have access to even see anything else.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_6f2ab446)

---

## Testing IAM Policies

### What I did in this step

In this step, I will log into our own AWS account as the intern and test access to the production and development instances because we want to make sure our intern doesn't have the ability to do anything that affects our production environment.



### Testing policy actions

I tested my JSON IAM policy by attempting to stop both the development and production instances.

### Stopping the production instance

When I try to stop the production instance. I was met with an error. This was because our production instance is tagged with the 'production' label, which is outside of the scope of our permission policy; interns are only to do things to the development environment.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_0e7a9d6a)

### Stopping the development instance

Next, when I tried to stop the development instance, I successfully saw the instance state change to stopping and then stopped.  This was because our permission policy allows the intern (i.e., users in the dev group) to stop the instance.


![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_1811801c)

---

## IAM Policy Simulator

To extend the project, I am going to test the permission policies in a safer and more controlled way—with a tool called the IAM policy simulator. I am doing this because having to stop instances and log into AWS accounts as other users is a bit disruptive. Let's find a more efficient way.


### Understanding the IAM Policy Simulator

IAM Policy Simulator is a tool that lets us simulate actions and test permission settings by defining a specific user/group/role and the action we want to test for. It is useful for saving time when testing permission settings; no more logging into another user or actually stopping resources.

### How I used the simulator

I set up a simulation for whether the dev user group has permission to stop the instance or delete tags. The results were denied for both—I had to adjust the scope of the EC2 instances to ones that are tagged with 'development.' Once I applied that tag, permission was allowed.

![Image](http://learn.nextwork.org/passionate_vermilion_joyful_wood_apple/uploads/aws-security-iam_069d8a621)

---

---
