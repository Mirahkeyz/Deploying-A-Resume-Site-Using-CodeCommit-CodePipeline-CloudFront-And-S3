# Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3

Scenario: Your team has asked you to create a way to automate the deployment of a website. Currently your developers have to go through the process manually to test each new update to their code. You’ll need to provide the static site URL to the developers and also make a modification to the code in the repo to verify that the pipeline is working.

# Foundational:
— Create a new repository in GitHub or CodeCommit and load the attached HTML.

— Create and configure an S3 bucket to host your static website.

— Create a CI/CD pipeline using the **AWS Codepipeline service **.

— Set your repo as the Source Stage of the Codepipeline that is triggered when an update is made.

— For the deploy stage select your S3 bucket.

— Deploy the pipeline and verify that you can reach the static website.

— Make an update to the code in your repo to verify that the code pipeline is triggered. This can be as simple as a change to the Readme file because any change to the files should trigger the workflow.

Let’s start by heading over to CodeCommit and creating a repo for the project. Click on Create repository, give it a name, optionally a description then click on Create.

![Snipe 1](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/3971326f-1ad3-4bf2-9888-0b6cd7d4b033)

Next we have to upload the provided HTML file into CodeCommit.

![Snipe 2](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/b98e8e2c-a900-4e00-a058-4d9b05adedda)

Now it’s time to create the S3 bucket to host our site.

Head over to S3 and create a new bucket and enable Static website hosting.

![Snipe 3](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/5139a6d5-15dc-40c8-b279-a60616d3a522)

Now we need to setup CodePipeline. Click Create pipeline, provide a name and select New service role.

![Snipe 4](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/5d4ca913-55da-445c-9835-b4a4194af606)

Click Next and give the Pipeline a name. Then expand the Advanced settings, select Custom location and choose the S3 bucket we just created.

![Snipe 5](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/c6e753f5-cf68-476e-b0c1-e8f689a22093)

In the next screen select AWS CodeCommit since that is where our file is located. For Repo name and Branch just click in the blank field and select the appropriate options. Leave everything else as default.

![Snipe 6](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/c9ae17af-5bef-4720-a792-9d017fd575a2)

Skip the build stage. In the Deploy stage choose the S3 bucket we created earlier. Tick Extract file before deploy box and click Next.

![Snipe 7](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/8db76e2c-2c5f-43b2-a09a-92dc1468cf8d)

Verify everything and when satisfied, click on Create pipeline.

After the pipeline finishes creating, it should Deploy to the S3 bucket.

![Snipe 8](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/2bd2d17a-333b-4362-adf3-a5f3880f2e7f)

Head over to the S3 bucket and grab the URL, open a new browser window or tab and paste the URL to see if the website is working.

And we are up and running!!!!

![Snipe 9](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/e051ecae-fe75-43c8-8d91-bffa365583a4)

Let’s open the website.html file in VSCode and make a change then upload it into our CodeCommit to test that the website can update

![Snipe 10](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/25a0c6e1-3c33-438d-a478-8e7fc9131870)

I will now upload the edited file into CodeCommit and see if CodePipeline is triggered…..

![Snipe 11](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/f1c3d385-6381-47c5-be8f-b183ee050ab8)

If everything worked properly we should be able to see the change to the website after refreshing the browser…..

![Snipe 12](https://github.com/Mirahkeyz/Deploying-A-Resume-Site-Using-CodeCommit-CodePipeline-CloudFront-And-S3/assets/134533695/d9bf9d51-0f0a-461c-86a4-0574cd86b895)














































