 Step 1: On the console search for s3 
 Step 2: click on create bucket 
 Step 3: Give a globally unique name to bucket
 Step 4: Block Public Access Settings
For private usage (e.g., website files used internally or with CloudFront):

✅ Keep all options checked (recommended for security)

For public access (e.g., hosting a static website):

❌ Uncheck “Block all public access”

✅ Acknowledge the warning checkbox

Step 5: Bucket Versioning (Optional)
Leave Disabled unless you want to keep file versions.

Step 6: Create the Bucket
Click the “Create bucket” button at the bottom.



✅Enable Static Website Hosting
If you're hosting a static site (HTML, CSS, JS):

Click the bucket name in S3 list.

Go to the “Properties” tab.

Scroll to “Static website hosting”, click Edit.

Enable it, and set:

Index document: index.html

Error document: error.html (optional)

Save changes.

> Upload Files to Your S3 Bucket
Click on the bucket name.

Click Upload → Add files → Choose your HTML/image/etc. files.

Click Upload.


Now your website is available at:
copy the dns endpoint 
http://<your-bucket-name>.s3-website-<region>.amazonaws.com/

