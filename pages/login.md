# Login to AWS using `aws-cli`

## For IAM User

1. If you are an IAM user, ask your __AWS Admin__ for an Access Keys which consists of you keys: `aws_access_key_id` and `aws_secret_access_key`.

2. Open your terminal to access the AWS CLI. Run `aws configure` to login. You will be asked for your keys.

3. You will be asked for the default region name. You must enter the region code instead of the name. The list of region codes can be found on [AWS Regions](https://docs.aws.amazon.com/AWSEC2/latest/UserGuide/using-regions-availability-zones.html). I will be choosing `ap-south-1` which the Mumbai Region.

4. Then specify the output type, which is `json` by default.

5. To test if everything was setup correctly, run `aws sts get-caller-identity`. The output JSON should contain a key named `Arn`, the value of this key can be verified from the `ARN` value of the user on the IAM console.

6. The AWS CLI config files can be found on `$HOME/.aws`

##  Granting IAM User CLI access

> [!IMPORTANT]
> _This part is for AWS Root/Admin users who want to allow IAM users to have AWS CLI access._

1. Navigate to  _IAM_ > _Users_ > _IAM User_

2. Click on the _Security Credentials_ tab and scroll down to _Acces Keys_ section where you can create a new access key.

3. There will be a list of _Use Cases_, select _Command Line Interface_ preset and scroll down to tick the _Confirmation_ checkbox. Hit on _Next_ to proceed.

4. You will land on the _Set description tag_ page where you can add an optional `tag` for the access keys if you want. Then Hit __Create Access Key__ to finish the process.

5. Copy the __Access key__ and __Secret access key__ from this page and share them with the IAM User or you can download the keys as a `CSV` and share the file with the IAM user.
