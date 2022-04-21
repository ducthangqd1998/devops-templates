// {
// 	"Version": "2012-10-17",
// 	"Statement": [
// 		{
// 			"Sid": "Upload, download and delete all objects in power-gen bucket",
// 			"Principal": "*",
// 			"Effect": "Allow",
// 			"Action": [
// 			    "s3:PutObject",
//                 "s3:GetObject",
//                 "s3:GetObjectVersion",
//                 "s3:DeleteObject",
//                 "s3:DeleteObjectVersion"
// 			],
// 			"Resource": "arn:aws:s3:::power-gen/*"
// 		}
// 	]
// }


server {
       listen 80;
       listen [::]:80;

       server_name example.com;

       root /var/www/example.com;
       index index.html;

       location / {
               try_files $uri $uri/ =404;
       }
}