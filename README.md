# Facebook SSL Pinning Bypass

Bypass Facebook SSL pinning on Android devices.  
Supported ABIs: `x86`, `x86_64`, `armeabi-v7a`, `arm64-v8a`

## Patched APK (No Root)

[facebook-v369.0.0.18.103-x86-patched](https://github.com/Eltion/Facebook-SSL-Pinning-Bypass/releases/download/v369.0.0.18.103/facebook-v369.0.0.18.103-x86-patched.apk)

[facebook-v369.0.0.18.103-x86_64-patched](https://github.com/Eltion/Facebook-SSL-Pinning-Bypass/releases/download/v369.0.0.18.103/facebook-v369.0.0.18.103-x86_64-patched.apk)

[facebook-v369.0.0.18.103-armeabi-v7a-patched.apk](https://github.com/Eltion/Facebook-SSL-Pinning-Bypass/releases/download/v369.0.0.18.103/facebook-v369.0.0.18.103-armeabi-v7a-patched.apk)

[facebook-v369.0.0.18.103-arm64-v8a-patched](https://github.com/Eltion/Facebook-SSL-Pinning-Bypass/releases/download/v369.0.0.18.103/facebook-v369.0.0.18.103-arm64-v8a-patched.apk)

[See all versions](https://github.com/Eltion/Instagram-SSL-Pinning-Bypass/releases/)

Note: You need to uninstall the Facebook app before trying to install it, if Facebook is installed as a system app then you can not uninstall it without root so this method will not work in that case.

## Run using Frida (Requires Root)

This method requires frida-tools and also frida-server running in the device
```
frida -U -l .\facebook-ssl-pinning-bypass.js -f com.facebook.katana --no-pause
```

## Intercept network traffic

You can use a tool like mitmproxy or Burp Suite to intercept the network.

1. Install patched APK in the device
2. Install [mitmproxy](https://mitmproxy.org/) or [Burp Suite](https://portswigger.net/burp)
3. Set up proxy for wifi settings or run: `adb shell settings put global http_proxy <proxy>`

Now you should be able to see the network traffic.

## View script logs
To view the logcat run:
```
adb logcat -s "FACEBOOK_SSL_PINNING_BYPASS:V"
```

[#leftenter](#leftenter)
