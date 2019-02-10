# TwitchStreamerDemo

Overview:

1. This demo is deployed on AWS using S3 static web hostinag in Ireland region.
2. Resources were deployed using serverless framework that uses Cloudformation stack to deploy this.
3. I am using "Twitch Embed Everything SDK" to fetch my favorite streamer's feed
   where, authentication would be performaed using twitch API.

Assumptions:
1. As this is only a demo, following assumption is made here:
   1. It is assumed that user will enter a valid streamer name, any wrong name
      will result in player error.
   2. Single user can use only single streamer name to watch the streamer feed.
   3. You have to refresh the page to enter another streamer.

Limitation:
   1. It is deployed in single region and performnce wont be good as it doesn't
      deploy any caching or other optimization like compression etc.

Improvements:
1. Using CloudFront with S3 will improve performance by caching the content and
   it can be accessed with same performance from anywhere in the world.

Scalability:
1. This deployment is scalable (900MM req/day) as S3 works based on diupto any number of request per second.

Cost:
1.With 900 million request per day roughly 2.7 billion request per month, it
would  cost around  $1200 per month.

Deployment instructions:
1. To deploy this demo , you need to make sure that all the serverless modules are installed (mentioned in serverless.yml)
2. You need to have aws cli configured with your  account credentials to access AWS.
