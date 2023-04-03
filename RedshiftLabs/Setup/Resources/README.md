**READ ME !!!**

1. AWS services file contains inforomation about aws services that are required for this lab.
2.  Redshift Data png file shows the environmental setup.
3. RedshiftENV.yaml file is a cloudformation templeate used to deploy the lab environment instead of manually creating it.
4. The RedshiftENV.yaml templete file needs to be ran on the CloudFormation stack as per shown below:

**Creating A CloudFormation stack:**

- Open the AWS CloudFormation console at https://console.aws.amazon.com/cloudformation.

- Create a new stack by using one of the following options:

- Choose **Create Stack**. This is the only option if you have a currently running stack.

- Choose **Create Stack** on the **Stacks** page. This option is visible only if you have no running stacks.

**Choosing a stack Template:**

On the Specify template page, choose a stack template by using one of the following options:

-Amazon S3 URL: Specify a URL to a template in an S3 bucket. (option that eas chosen for the lab)

- Upload a template file: Select a CloudFormation template on your local computer.

- Use a sample template : Select a sample template from a collection of templates provided by CloudFormation to get you started.
- skip other configuration then click create.

**Setting up Redshift Query Editor as the Redshift Client:**

Once all the resources have been successfully created, Qeury Editor2 can be used connect to the Redshift cluster:

- On the left-hand side, click on the Redshift environment you want to connect to.
- A pop-up window should have opened.

Enter the Database name and user name. Click connect. These credentials should be used for both the Serverless endpoint (workgroup-xxxxxxx) as well as the provisioned cluster (consumercluster-xxxxxxxxxx).


