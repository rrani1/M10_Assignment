# M10_Assignment

Part I: Create web-scraper to load CSV file into S3 Bucket
Step 1: Load the script into your repository
Create a new repository named "M10_Assignment" on GitHub.
Inside the repository, create the following folders: images, files, and scripts.
Upload the M10_webscraper_assignment.ipybn script to the scripts folder.
Step 2: Create an S3 bucket
Install and configure awscli and boto3.
Create an S3 bucket using the AWS Management Console or CLI. Let's assume you name it "database-update-bucket."
Step 3: Update the script to include your S3 path
Open the script M10_webscraper_assignment.ipybn using a text editor or Jupyter Notebook.
Locate the part of the script where the S3 path is specified and update it with your bucket name.
Step 4: Test the script
Run the script and inspect the output on your S3 bucket.
Ensure that the CSV file is successfully uploaded to the specified S3 path.
Step 5: Commit changes to GitHub
Commit the changes to the master branch of your GitHub repository.
Step 6: Remove the blank row in the CSV output file
Identify the part of the script that generates the CSV file and modify it to remove the blank row in the header.
Step 7: Test the modified script
Run the modified script and inspect the output on your S3 bucket.
Ensure that the CSV file now has no blank row in the header.
Step 8: Commit changes to GitHub
Commit the changes to the master branch of your GitHub repository.
Step 9: Provide evidence of successful update
Share the link to your S3 bucket where the CSV file is stored.
Provide the link to the updated M10_webscraper_assignment.ipybn file in your GitHub repository.
Step 10: Update README.md
Update the README.md file in your repository to reflect the script actions, changes made, and proper documentation.

Part II: Update web-scraper to iterate all results
Step 11: Modify the script for pagination
Alter the script to iterate through the pagination on the Charities Bureau Website.
Compile all results into one dataframe from each page.
Step 12: Test the modified script
Run the modified script and inspect the output on your S3 bucket.
Ensure that the CSV file contains data from all pages without skipped headers.
Step 13: Commit changes to GitHub
Commit the changes to the master branch of your GitHub repository.
Step 14: Add instructor as a collaborator
Add your instructor as a collaborator to the GitHub repository.
Step 15: Submit the assignment
Reply to the assignment with the link to your GitHub repository.
