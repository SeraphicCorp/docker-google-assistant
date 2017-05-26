# Instructions

## Thanks to Google for making this available
https://github.com/googlesamples/assistant-sdk-python/tree/master/google-assistant-sdk
https://developers.google.com/assistant/sdk/prototype/getting-started-other-platforms/config-dev-project-and-account

## Steps to use
- Create an Google account if you do not already have one
- Go to https://console.cloud.google.com/ to create a new project
- Go to API Management and activate the API Google Assistant and follow the given instructions (for the platform, use command line interface). During the process, you will have to create an OAuth 2.0 ID in JSON, download this file



# Run
docker run -it -v ./google-assistant/:/google-assistant --net host --device /dev/snd --name google-assistant multiarch/debian-debootstrap:armhf-jessie