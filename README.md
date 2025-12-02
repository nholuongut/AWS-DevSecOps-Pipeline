## AWS DevSecOps Pipeline

![](https://i.imgur.com/waxVImv.png)
### [View all Roadmaps](https://github.com/nholuongut/all-roadmaps) &nbsp;&middot;&nbsp; [Best Practices](https://github.com/nholuongut/all-roadmaps/blob/main/public/best-practices/) &nbsp;&middot;&nbsp; [Questions](https://www.linkedin.com/in/nholuong/)
<br/>

[![Typing SVG](https://readme-typing-svg.demolab.com?font=Fira+Code&weight=500&size=24&pause=1000&color=F7931E&width=435&lines=Hello%2C+I'm+Nho+Luong🇻🇳🇻🇳🇻🇳🇻🇳🇻)](https://git.io/typing-svg)

# **About Me🇻**
- ✍️ Blogger
- ⚽ Football Player
- ♾️ DevOps Engineer
- ⭐ Open-source Contributor
- 😄 Pronouns: Mr. Nho Luong
- 📚 Lifelong Learner | Always exploring something new
- 📫 How to reach me: luongutnho@hotmail.com

This DevSecOps pipeline uses AWS DevOps tools CodeBuild, AWS CodeCommit, AWS CodeDeploy, and AWS CodePipeline along with other AWS services.  It is highly recommended to fully test the pipeline in lower environments and adjust as needed before deploying to production.

### Build and Test: 
AWS Buildspec and property files for security vulnerability scanning:
* buildspec-owasp-depedency-check.yml: buildspec file to perform SCA analysis using OWASP Dependency-Check.
* buildspec-sonarqube.yml: buildspec file to perform SAST analysis using SonarQube.
* buildspec-phpstan.yml: buildspec file to perform SAST analysis using PHPStan. This opensource tool is only applicable for scanning PHP application.
* buildspec-owasp-zap.yml: buildspec file to perform DAST analysis using OWASP Zap.
* Composer.json: PHP package manager for installing PHPStan and dependencies.
* phpstan.neon: configuration file for PHPStan.
* Sonar-project.properties: SonarQube configuration file.

### Lambda files:
#### AWS lambda is used to parse the security scanning results and post them to AWS Security Hub
* import_findings_security_hub.py: to parse the scanning results and extract the vulnerability details.
* securityhub.py: to post the vulnerability details to AWS Security Hub in ASFF format (AWS Security Finding Format).

### CloudFormation for Pipeline:
* codepipeline-template.yml: CloudFormation template to deploy DevSecOps CICD Pipeline 

## Deploying pipeline:
Download the CloudFormation template and pipeline code from GitHub repo.

1.	Log in to your AWS account if you have not done so already. 
2.	On the CloudFormation console, choose Create Stack. 
3.	Choose the provided CloudFormation pipeline template. 
4.	Choose Next.
5.	Provide the stack parameters:
    *  Under Code, provide code details, such as repository name and the branch to trigger the pipeline.
    *	Under SAST, choose the SAST tool (SonarQube or PHPStan) for code analysis, enter the API token and the SAST tool URL. You can skip SonarQube details if using PHPStan as the SAST tool.
    *	Under DAST, choose the DAST tool (OWASP Zap) for dynamic testing and enter the API token, DAST tool URL, and the application URL to run the scan.
    *	Under Lambda functions, enter the Lambda function S3 bucket name, filename, and the handler name.
    *	Under STG Elastic Beanstalk Environment and PRD Elastic Beanstalk Environment, enter the Elastic Beanstalk environment and application details for staging and production to which this pipeline deploys the application code. 
    *	Under General, enter the email addresses to receive notifications for approvals and pipeline status changes. 


Note: The provided CloudFormation template in this blog is formatted for AWS GovCloud, if you are setting this up in standard region, you will have to adjust the partition name in the CloudFormation template. For example, change arn values from “arn:aws-us-gov” to “arn:aws”. 


## License
Copyright Amazon.com, Inc. or its affiliates. All Rights Reserved.
SPDX-License-Identifier: MIT-0

![](https://i.imgur.com/waxVImv.png)
# I'm are always open to your feedback🚀
# **[Contact Me🇻]**
* [Name: Nho Luong]
* [Telegram](+84983630781)
* [WhatsApp](+84983630781)
* [PayPal.Me](https://www.paypal.com/paypalme/nholuongut)
* [Linkedin](https://www.linkedin.com/in/nholuong/)

![](https://i.imgur.com/waxVImv.png)
![](Donate.png)
[![ko-fi](https://ko-fi.com/img/githubbutton_sm.svg)](https://ko-fi.com/nholuong)

# License🇻
* Nho Luong (c). All Rights Reserved.🌟


