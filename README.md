# THIS PROJECT DEMONSTRATES HOW TO DEPLOY STATIC WEBSITE ON AN S3 BUCKET AND DISTRIBUTE USING CLOUDFRONT

#### __Services Required__
#### - S3 - to create bucket and upload source code
#### - Cloud front -AWS global content delivery network, that speeds up distribution of your static and dynamic web content (such as .html, .css, image and .js files) to your users 
#### - Cloud Provider = AWS

#### 1. Login to your AWS account, from the management console's home page, search for s3 using the searchbar or from recently visited or from list of favorites (click on s3)
![](Images/sh1.png)
#### 2. On s3 dashboard, click the create bucket button to create a bucket
![](images/sh2.png)
#### 3. Give bucket a unique global name, 
![](images/sh3.png)
#### 4. Disable block public access settings for this bucket, so as to make this bucket publicly visible, then acknowledge.
![](images/sh4.png)
#### 5. Bucket is created
![](images/sh5.png)
#### 6. Upload files to the bucket either using drap and drop, the upload button or awscli
#### I used awscli to upload really big folders
#### aws s3 cp vendor/ s3://my-bucket-202203081/vendor/ --recursive 
#### aws s3 cp css/ s3://my-bucket-202203081/css/ --recursive 
#### aws s3 cp img/ s3://my-bucket-202203081/img/ --recursive 
![](images/sh6.png)
#### 7. Go to permissions tab to secure bucket via IAM
![](images/sh7.png)
#### 8. Edit bucket policy and ensure resource is the current bucket's name
![](images/sh8.png)
#### 9. Notice the objects in the bucket are now _publicly accessible_ (this is required for static website hosting)
![](images/sh9.png)
#### 10. Click __edit static website hosting__ and enable static website hosting, then specify your index and error document/page. I used index.html as my index and error document.
![](images/sh10.png)
#### 11. Copy bucket website endpoint and paste on a browser
![](images/sh11.png)
#### 12. Notice that the website is visible using the bucket website endpoint
![](images/sh12.png) 
#### 13. Search for cloudfront on the searchbar
![](images/sh13.png)
#### 14. On cloudfront's dashboard, click on create a cloudfront distribution 
![](images/sh14.png)
#### 15. Name origin domain with _bucket website endpoint_ (do not select from dropdown), leave other fields with their default values
![](images/sh15.png)<br/><br/>
![](images/sh16.png)
#### 16. Cloudfront distribution has been created, and is still in __deploying__ state
![](images/sh17.png)
#### 17. Cloudfront state is now in deployed copy domain name and paste on the browser

![](images/sh18.png)
#### 18. The website can be accessed via:
#### __website endpoint__
![](images/sh12.png)
#### OR THE __cloudfront URL__
![](images/sh18.png)


#### I cleaned up by deleting the objects (files) in my bucket and deleting my cloudfont distribution.
