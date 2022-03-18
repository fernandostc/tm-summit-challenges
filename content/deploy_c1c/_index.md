---
title: "Deploy Cloud One - Conformity"
chapter: false
weight: 20
pre: "<b>2. </b>"
---

### Deploy Cloud One - Conformity

After you create a Trend Micro Cloud One account, the next step is to integrate your AWS account with Conformity to gain deep visibility around the possible drifts and misconfiguration within over 80 different AWS services. It will also check that your infrastructure aligns with the AWS Well-Architected Framework too :star_struck:


#### Log in to Trend Micro Cloud One and go to Conformity

**1.** Upon signing into Trend Micro Cloud One, you’ll be prompted to select between the seven security solutions in Trend Micro Cloud One platform. Today, we will be using Conformity

![Integration1](/images/integration1.png) 

![Integration2](/images/integration2.png) 

---

**2.** After selecting Conformity, you can begin adding your AWS account by clicking <b>Add Account</b>. There are two ways to link your account: automatically or manually.

![Integration3](/images/integration3.png) 

![Integration4](/images/integration4.png) 

---

**3.** First, you will need to define the account name and environment type of the AWS account that you will integrating with Conformity to make it easy to locate the account inside the dashboard. For further detail and additional assistance, please refer to the help video in the page:

- In our case we are using the Account Name: <code>AWS Modernization Workshop</code>

![Integration5](/images/integration5.png) 

---

**4.** To link your account, either automatically or manually, a dedicated IAM role with two custom policies will be created in order to enable <b>Cross-Account Access</b>. To verify the IAM role and the type of access necessary to use it, click <b>Manual setup</b> and review the attached custom policies.

![Integration6](/images/integration6.png) 

![Integration8](/images/integration8.png) 


---

**5.** Follow the automation instructions regarding AWS setup. After selecting <b>Launch Stack</b>, you’ll be taken to your AWS management console and prompted to check <b>I acknowledge…</b> After a few moments, a CloudFormation stack will be created. Upon creation, go to <b>Outputs</b>, copy the <b>CloudConformityRoleArn</b> and paste into the box in Conformity:

![Integration7](/images/integration7.png) 

![Integration9](/images/integration9.png) 

![Integration10](/images/integration10.png) 

---

**6.** After adding the ARN to Conformity click <b>Next</b>. Now you have successfully added your AWS account  :cloud: :smile:

![Integration11](/images/integration11.png) 

---

**7.** The Conformity bot will automatically launch a scan upon completion. After the scan has completed, you have successfully set up your account.

![Integration12](/images/integration12.png) 

---

**8.** Now you are all set up and you will be able to see the results after couple minutes in the dashboard like the image below:

![Integration13](/images/integration13.png) 

---

**Let's build our first report in Cloud One - Conformity!!** :laptop::bar_chart: