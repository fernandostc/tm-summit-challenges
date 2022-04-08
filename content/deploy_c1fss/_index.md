---
title: "Deploy Cloud One File Storage Security"
chapter: true
weight: 20
pre: "<b>3. </b>"
---


# Deployment

### Cloud One - File Storage Security Deployment

The best way to learn is to get our hands dirty, so let’s deploy Cloud One - File Storage Security to our AWS Account. First, make sure that all the requirements are met, then:

**1.** Login to the [Cloud One platform](https://cloudone.trendmicro.com). It will request the login information for Cloud One. If you don’t have it, check the requirements page which has all the details you will need to create your account.

![Diagram](/images/login.png)

---

**2.** Select the File Storage Security tile
![Diagram](/images/login_2.png)

---

**3.** Click on Stack management in your left side
![Diagram](/images/login_3.png)

---

**4.** Click on "Deploy" 
![Diagram](/images/login_4.png)

---

**5.** Select ```Scanner Stack and Storage Stack```, to deploy the full solution to your AWS account.

![Diagram](/images/fss-deploy-stacks-select.png)

---

**6.** Select the AWS region that best suits you ([AWS regions supported](/10_requirements.html)) and click on ```Launch Stack```, this will redirect you to your AWS account in the region that you choose to deploy the stack. Make sure that you're logged in and have the correct permissions - you can check the details of the permissions required in the Requirements section.

{{% notice tip %}}
Try to make sure the Cloud One console tab is in the same Window as your browser, so Launch Stack will automatically use the AWS session that you have open already. 
{{% /notice %}}

You can validate the Cloud Formation Template by clicking in ```Review Stack```, to make it easier, you can also verify the Cloud Formation Template by clicking the buttons below:

{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/aws/FSS-All-In-One.template" %}}All in One Template{{% /button %}}
{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/aws/FSS-Scanner-Stack.template" %}}Scanner Stack{{% /button %}}
{{% button href="https://github1s.com/trendmicro/cloudone-filestorage-cloudformation-templates/blob/master/aws/FSS-Storage-Stack.template" %}}Storage Stack{{% /button %}}

![Diagram](/images/login_5.png)

---

**7.** In the CloudFormation page the <b>only required parameter</b> here is the <b>name of bucket</b> that you choose to be scanned. In our case please <b>search on the AWS Event Engine account for the Bucket name</b> <span style="color:red"><b>AWS-Summit-***</b></span> - this is the name from the S3 bucket that was created as a blueprint from your lab account. 

After adding the bucket name based on your AWS event engine account you will need to acknowledge and click on <b>"Create Stack"</b>:

{{% notice warning %}}
<p style='text-align: left;'>
Remember to update the S3BucketToScan with the AWS S3 Bucket name <b>AWS-Summit-***</b> that you can find into your AWS lab provided for the challenge.
</p>
{{% /notice %}}

![Diagram](/images/cftdeploy.png)

---

#### **8.** Gathering the ARNs
After deploying the all-in-one stack in your AWS account, you must configure the scanner and storage stack Amazon Resource Names (ARNs) information in the Cloud One console. The ARNs map a scanner stack to a storage stack, allowing them to be aware of each other.

Go to CloudFormation > Stacks > your all-in-one stack > Outputs tab and copy the Value with these Key names here ```ScannerStackManagementRoleARN``` and ```StorageStackManagementRoleARN``` and paste the information into the Cloud One - File Storage Security console.

![Diagram](/images/fss-arn-aws-info.png)

![Diagram](/images/login_6.png)

---

**9.** Then Click <b>Submit</b>. You see a couple of success messages at the bottom and the stack will show in the Stack Management too. 

![Diagram](/images/login_7.png)

You have now completed the deployment of the All-in-One stack :tada:, to protect S3 buckets against Ransomware and Malware. 

It will now start scanning any new object uploaded to S3 buckets now on. 

The objects will be automatically tagged as "malicious" or "no issues found" based in our malware engines. 

----

**Now let's deploy the cloud misconfiguration detection tool!!** :laptop::bar_chart:



