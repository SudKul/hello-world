# hello-world



### 5. Exercise - Rollback
Files relevant for this exxercise are:

1. *.circleci/config.yml* - Look out for the *create_infrastructure*  job and *destroy_environment* command. 
2. *template.yml*


### 6. Exercise: Promote to Production
Prerequisite: An S3 bucket (say `mybucket644752792305`) containing a sample index.html file created manually in your AWS console. Use the command below to create a  CloudFront Distribution
```bash
 aws cloudformation deploy \
 --template-file cloudfront.yml \
 --stack-name production-distro \
 --parameter-overrides PipelineID="mybucket644752792305"
 ```

1. *.circleci/config.yml* - Look out for the jobs having "Exercise: Promote to Production" comment.

2. *cloudfront.yml* - Creates a Cloudfront Distribution will connect to the existing bucket. We are assuming that the `PipelineID` parameter represents the bucket name. 

3. *bucket.yml* - Creates a **new** bucket and bucket policy. 