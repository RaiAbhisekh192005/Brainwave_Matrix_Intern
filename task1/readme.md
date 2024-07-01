# Boxing Web Application Deployment

This README file provides a step-by-step guide to deploy the Boxing Web Application using AWS EC2 and S3.

## Prerequisites

- An AWS EC2 instance running Amazon Linux.
- An S3 bucket containing your web application files in a ZIP archive.

## Deployment Steps

1. **Switch to the root user:**
    ```
    sudo su -
    ```

2. **Update the package index:**
    ```
    yum update -y
    ```

3. **Install the Apache web server:**
    ```
    yum install -y httpd
    ```

4. **Check the status of the Apache service:**
    ```
    systemctl status httpd
    ```

5. **Enable the Apache service to start on boot:**
    ```
    systemctl enable httpd
    ```

6. **Start the Apache service:**
    ```
    systemctl start httpd
    ```

7. **Create a temporary directory:**
    ```
    mkdir temp
    ```

8. **Navigate to the temporary directory:**
    ```
    cd temp
    ```

9. **Download the ZIP file from your S3 bucket:**
    ```
    wget "object URL of S3"
    ```

10. **List the contents to verify the download:**
    ```
    ls
    ```

11. **Unzip the downloaded file:**
    ```
    unzip "filename.zip"
    ```

12. **Navigate to the unzipped folder:**
    ```
    cd "folder name"
    ```

13. **Move the web application files to the Apache document root:**
    ```
    mv * /var/www/html
    ```

14. **Navigate back to the temporary directory:**
    ```
    cd temp
    ```

## Conclusion

Your Boxing Web Application should now be deployed and accessible via the public IP address of your EC2 instance. You can verify the deployment by opening a web browser and navigating to `http://<your-ec2-public-ip>`.
