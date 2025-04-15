# Test Project to use and learn AWS Textract
- Accesses AWS Textract by deploying a lambda function
1. Create lambda function with proper accesses
   - Added the inline policy to access DetectDocumentText (do this only if you want just local image text extraction)
   - Added the inline policy to access S3 buckets (to use s3 buckets)
     - Make sure to specify the correct s3 bucket ARN
     - *S3 and lambda must be in the same region*
     - *use pdf for images*
2. Deploy the lambda function code
   - Go to the Code tab in the lambda function
   - Add the lambda_handler code into the <lambda-name> lambda_function.py
   - Deploy
3. Test lambda function
   - Ensure the user has the InvokeLambda function access (either by adding a user to a user group with the InvokeLambda policy or directly attaching the policy)
   - Create client code (textract_test.py) to run/test the lambda function code
   - run python3 textract_test.py textract-lambda (s3://bucket/path/document.jpg or local path to image file)
  
Tips:
- Ensure everything has the correct policies attached for access
- Ensure the lambda function and s3 are in the same region and specified the correct s3 arn for the lambda access
- Ensure you are calling the function correctly

# Source
https://docs.aws.amazon.com/textract/latest/dg/lambda.html
