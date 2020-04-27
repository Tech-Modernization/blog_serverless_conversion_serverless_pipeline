# Summary
Cloudformation template that creates a codepipeline for serverless deployment

# Features of the codepipeline:
* Build the application in a codebuild container.
* Deploy application to a dev ServerLess application.
* Test the dev ServerLess application using codebuild.
* Deploy application to a prod ServerLess application.

# Create the codepipeline
```
aws cloudformation deploy --stack-name cpStackServerless --template-file codepipeline_template.yml \
        --capabilities CAPABILITY_IAM CAPABILITY_AUTO_EXPAND \
        --parameter-overrides \
        GitHubUser=<github userid> \
        GitHubRepo=<github repo name> \
        GitHubBranch=<repo branch> \
        GitHubToken=<github personal token> \
        CloudWatchLogGroup="cloudwatch log group for CodeBuild" \
        CloudWatchLogStream="cloudwatch log stream for CodeBuild"
```

# Update the application
Push a change to the application repo branch, the codepipeline should execute.

