# openshift-nested-cloudformation-deployment
Nested deployment stack for OpenShift 4 on AWS using user-provisioned infrastructure.

Instructions
1. Download and customise the Redhat-provided CloudFprmation scripts at https://docs.openshift.com/container-platform/4.1/installing/installing_aws_user_infra/installing-aws-user-infra.html

2. Follow instrauctions at at the above page and upload customised templates to an s3 bucket of your choice. Sample templates available in cf_templates/.

3. Complete ocp_nested_deployment_params_nprod.json with all required fields

4. Execute custom template:
    
    aws cloudformation create-stack --stack-name "ocp-nested-stack-`date +%H%M%S`" --template-body file:///path/to/ocp_nested_deployment_stack_nprod.yaml --parameters file:///path/to/ocp_nested_deployment_params_nprod.json --capabilities CAPABILITY_NAMED_IAM