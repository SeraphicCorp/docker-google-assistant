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
docker run -it -v absolute-path-to-folder-with-your-clientid.json:/google-assistant --net host --device /dev/snd --name google-assistant seraphiccorp/google-assistant

## Troubleshooting
If you have troubles with the microphone, it may look like that :
```
Traceback (most recent call last):
  File "/env/bin/googlesamples-assistant-audiotest", line 11, in <module>
    sys.exit(main())
  File "/env/lib/python3.4/site-packages/click/core.py", line 722, in __call__
    return self.main(*args, **kwargs)
  File "/env/lib/python3.4/site-packages/click/core.py", line 697, in main
    rv = self.invoke(ctx)
  File "/env/lib/python3.4/site-packages/click/core.py", line 895, in invoke
    return ctx.invoke(self.callback, **ctx.params)
  File "/env/lib/python3.4/site-packages/click/core.py", line 535, in invoke
    return callback(*args, **kwargs)
  File "/env/lib/python3.4/site-packages/googlesamples/assistant/grpc/audio_helpers.py", line 371, in main
    flush_size=audio_flush_size)
  File "/env/lib/python3.4/site-packages/googlesamples/assistant/grpc/audio_helpers.py", line 187, in __init__
    blocksize=int(block_size/2),  # blocksize is in number of frames.
  File "/env/lib/python3.4/site-packages/sounddevice.py", line 1491, in __init__
    **_remove_self(locals()))
  File "/env/lib/python3.4/site-packages/sounddevice.py", line 1017, in __init__
    'Error opening {0}'.format(self.__class__.__name__))
  File "/env/lib/python3.4/site-packages/sounddevice.py", line 2671, in _check
    raise PortAudioError(msg)
sounddevice.PortAudioError: Error opening RawStream: Invalid sample rate
```

Then create a file called asoundrc.config in the same folder as clientid.json and follow the recommandations from https://developers.google.com/assistant/sdk/prototype/getting-started-pi-python/configure-audio. You can launch all these commands directly from the RPI as the configuration is shared with the container.