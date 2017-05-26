# Instructions

## Thanks to Google for making this available
- https://github.com/googlesamples/assistant-sdk-python/tree/master/google-assistant-sdk
- https://developers.google.com/assistant/sdk/prototype/getting-started-other-platforms/config-dev-project-and-account

## Steps to use
* You will need a microphone connected by USB (Directly or through a USB soundcard) so connect it now
* Create a Google account if you do not already have one
* Go to https://console.cloud.google.com/ to create a new project
* Go to API Management and activate the API Google Assistant and follow the given instructions (for the platform, use command line interface). During the process, you will have to create an OAuth 2.0 ID in JSON, download this file

If you need help, please use the links provided on top of this document.


## Run
docker run -it -v folder-with-your-clientid.json:/google-assistant --net host --device /dev/snd --name google-assistant seraphiccorp/google-assistant