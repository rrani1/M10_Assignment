# Load libraries
import awscli
import selenium
import boto3
import pandas as pd
import time

from selenium import webdriver

# SCRAPE THE WEBSITE
# Call the webdriver
browser = webdriver.Chrome(r"C:\Users\Rekha Chaudhary\Downloads\chromedriver-win64\chromedriver-win64\chromedriver.exe")

# Enter the URL path that needs to be accessed by webdriver
browser.get('https://www.charitiesnys.com/RegistrySearch/search_charities.jsp')

# Identify xpath of location to select element
inputElement = browser.find_element('xpath', "/html/body/div/div[2]/div/table/tbody/tr/td[2]/div/div/font/font/font/font/font/font/table/tbody/tr[4]/td/form/table/tbody/tr[2]/td[2]/input[1]")
inputElement.send_keys('0')
inputElement1 = browser.find_element('xpath', "/html/body/div/div[2]/div/table/tbody/tr/td[2]/div/div/font/font/font/font/font/font/table/tbody/tr[4]/td/form/table/tbody/tr[10]/td/input[1]").click()

# Identify the table to scrape
table = browser.find_element('css selector', 'table.Bordered')

print(table)

# Create empty dataframe
df = []

# Locate the table
table = browser.find_element(By.CSS_SELECTOR, 'table.Bordered')

# Locate the rows inside the table using By.TAG_NAME
rows = table.find_elements(By.TAG_NAME, 'tr')

# Loop through dataframe to export table
for row in rows:
    cols = df.append([cell.text for cell in row.find_elements(By.TAG_NAME, 'td')])

# Update dataframe with header
df = pd.DataFrame(df[1:], columns=["Organization Name", "NY Reg #", "EIN", "Registrant Type", "City", "State"])

# Display the DataFrame in tabular format
display(df)

import pandas as pd
import boto3
import time



# Construct S3 key (object key)
s3_key = 'charities_bureau_scrape_' + time.strftime("%Y%m%d%H%M%S") + '.csv'

# Load file into S3
df.to_csv(s3_key, header=True, index=False)

# Specify your S3 bucket name
bucket_name = 'database-update-bucket-rani'

# Explicitly set AWS credentials and region
aws_access_key_id = 'AKIA4OPMEVP4AQPSEP7N'
aws_secret_access_key = 'r65xsgrxIsVGA4wMfhzOFJHPKyWQZdFyTk+VAdkP'
region_name = 'us-east-1'  # Replace with your region

# Create an S3 client
s3 = boto3.client('s3', aws_access_key_id=aws_access_key_id, aws_secret_access_key=aws_secret_access_key, region_name=region_name)

# Upload the file to S3
s3.upload_file(s3_key, bucket_name, s3_key)

# Print success message
print("Successfully uploaded file to S3 with key: " + s3_key)
