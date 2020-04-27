# Summary
Cloudformation template that creates a codepipeline for serverless deployment

# to create codepipeline
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

# Summary
Cloudformation template that creates an AWS codepipeline. The pipeline gets its source from a github repo, deploys to a dev serverless application, test the dev application, and deploy to the prod serverless application.

# Update the application
Push a change to the application repo branch, the codepipeline should execute.

