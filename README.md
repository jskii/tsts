# TweetStreamToSlack (tsts)
A simple dotnet app to capture tweets from a Twitter list and send them to a Slack channel you provide. Great for keeping track of stuff without obviously looking at Twitter!

## Prerequisites 
### Only required for local debug/dotnet 3.1 usage
1. dotnet core 3.1
1. TweetInvi library installed from NuGet - Install-Package TweetInvi
### Required for Docker usage
1. Setup Twitter application to get a workable CONSUMER_KEY, CONSUMER_SECRET, ACCESS_TOKEN, ACCESS_TOKEN_SECRET (https://apps.twitter.com)
1. Setup incoming Slack webhook to a channel in the group you want, to display the information you pass
1. Collect credentials and pass them as environment variables; either using -e and docker run, or into the docker-compose file included

## Usage
- Modify `docker-compose.yaml` to include the values needed for the application to run from prerequisite step; everything in `environment` block must have a value!
- Once all values are set in the compose file, `docker-compose up` will run everything for you, including pulling image from Dockerhub

## Notes
To keep your environment values in docker-compose.yaml but not risk them being included in the repo if you fork/use your own:
`git update-index --assume-unchanged docker-compose.yaml`