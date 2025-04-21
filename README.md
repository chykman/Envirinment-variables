

# AWS Environment Switching Utility

## Description

`aws_cloud_manager.sh` is a **Bash script** that provides a secure and efficient way to switch between different AWS environments such as **local**, **testing**, and **production**. By using structured functions, it ensures that the correct AWS CLI profile is activated based on the specified environment, while also performing necessary checks to maintain security and prevent errors.

Managing multiple AWS environments can be challenging, especially when dealing with **sensitive credentials and configurations**. This script addresses these challenges by compartmentalizing risks through **modular functions**, each serving a specific protective role. This improves security, readability, and maintainability.

---

## Setup

To use this script effectively, ensure your AWS credentials and configurations are properly set up:

### Credentials

Store your AWS access keys in `~/.aws/credentials`, using **separate profiles** for each environment:

```ini
[testing]
aws_access_key_id = YOUR_TESTING_ACCESS_KEY
aws_secret_access_key = YOUR_TESTING_SECRET_KEY

[production]
aws_access_key_id = YOUR_PRODUCTION_ACCESS_KEY
aws_secret_access_key = YOUR_PRODUCTION_SECRET_KEY
```

### Configurations

Define region and output settings in `~/.aws/config`:

```ini
[profile testing]
region = us-west-2
output = json

[profile production]
region = us-east-1
output = json
```

### File Permissions

Ensure that the credentials file is secure:

```bash
chmod 600 ~/.aws/credentials
```

---

## Script Overview

The `aws_cloud_manager.sh` script is modular, with each function performing a specific task:

- `check_aws_cli()`: Verifies that the AWS CLI is installed.
- `check_aws_profile()`: Validates that the specified AWS profile exists and is configured.
- `activate_infos_environment()`: Switches to the specified environment using a case statement.
- `check_num_of_args()`: Ensures exactly one argument is provided.

---

## Function Details

### `check_aws_cli()`

- Verifies the presence of the AWS CLI using `aws --version`.
- Exits the script with an error if the CLI is not installed.

### `check_aws_profile()`

- Uses the `-z` test to ensure the profile is provided and not empty.
- Confirms the profile exists in AWS configuration files.

### `activate_infos_environment()`

- Uses a `case` statement to handle switching between `local`, `testing`, and `production`.
- Sets the appropriate AWS CLI profile.
- Ensures only valid environments are accepted.

### `check_num_of_args()`

- Ensures the script receives exactly one argument (environment name).
- If not, displays a usage message and exits.

---

## Usage Examples

### Switch to Testing Environment

```bash
./aws_cloud_manager.sh testing
```

Activates the `testing` AWS CLI profile.

### Switch to Production Environment

```bash
./aws_cloud_manager.sh production
```

Activates the `production` AWS CLI profile.

### Attempt to Switch to an Invalid Environment

```bash
./aws_cloud_manager.sh invalid
```

Displays an error and exits — `invalid` is not a recognized environment.

---

## Additional Notes

### Security Best Practices

- Keep your AWS credentials secure.
- Use IAM roles and policies for **least privilege**.
- Regularly rotate access keys.
- Never share your credentials.

### Dependencies

Ensure the AWS CLI is installed:

```bash
sudo apt install awscli
```

### Troubleshooting

If you encounter issues:

- Verify AWS credentials and config files.
- Ensure the script has execute permissions:

```bash
chmod +x aws_cloud_manager.sh
```

- Check script output for error messages and act accordingly.

---

## Script Simplification

The script is a **simplified example** to illustrate concepts. In production, consider adding:

- More robust **error handling**
- **Logging**
- Integration with **other tools or services**

---

## Conclusion

`aws_cloud_manager.sh` offers a **secure and efficient** method for managing AWS environments through structured functions. By compartmentalizing tasks like:

- Checking the AWS CLI
- Validating profiles
- Switching environments
- Verifying arguments

...the script ensures reliability, clarity, and security. Adopting similar practices helps manage cloud infrastructure effectively and reduces the risk of errors in production.

---

### Screenshots

![Environment Setup Screenshot 1](https://github.com/user-attachments/assets/72a0997c-5983-42cd-919f-120e15179b40)

![Environment Setup Screenshot 2](https://github.com/user-attachments/assets/edea23e3-164e-445a-97c6-071dd61843d4)

![Environment Setup Screenshot 3](https://github.com/user-attachments/assets/56ce0d51-4beb-43f6-a515-d4ae1370c873)

---
