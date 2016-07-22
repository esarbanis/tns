# Docker image for NativeScript development

## How to use it
Alias the following command as tns or create a script out of it:

```
docker run -it --rm --privileged -v /dev/bus/usb:/dev/bus/usb -v $PWD:/src esarbanis/tns tns
```

If you go with the scripting solution add $@ at the end to pass all arguments.