## Capmonster.cloud for Python 
![GitHub top language](https://img.shields.io/github/languages/top/alperensert/python_capmonster) ![GitHub release (latest by date)](https://img.shields.io/github/v/release/alperensert/python_capmonster) ![PyPI - Downloads](https://img.shields.io/pypi/dw/capmonster_python) ![GitHub](https://img.shields.io/github/license/alperensert/python_capmonster) ![GitHub Repo stars](https://img.shields.io/github/stars/alperensert/python_capmonster?style=social) 

Capmonster.cloud library for Python3. <br/>
Currently supporting ImageToText, NoCaptcha (Recaptcha v2) proxyless and proxy-on, Recaptchav3Proxyless, FunCaptcha proxyless and proxy-on, HCaptcha proxyless and proxy-on.<br/>
##### At least 2x cheaper, up to 30x faster than manual recognition services.

```
pip install capmonster_python
```

IMPORTANT
-
- If you get an CapmonsterException error, please recreate your task and keep going like that.
- Use latest version, update your module.
- If you are using a version higher than 1.2.1, change imports python_capmonster to this like that:
```python
from capmonster_python import *
```

### Documentation
You can find documentation in [here](https://github.com/alperensert/python_capmonster/blob/master/docs/documentation.md).

### Examples
##### *ImageToTextTask*
- Send image without encode.
```python
from capmonster_python import ImageToTextTask

capmonster = ImageToTextTask(client_key="YOUR CLIENT KEY")
taskId = capmonster.createTask(file_path="captcha.png")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
- Send directly image encoded data.
```python
from capmonster_python import ImageToTextTask

capmonster = ImageToTextTask(client_key="YOUR CLIENT KEY")
taskId = capmonster.createTask(base64_image="DATA")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *NoCaptchaTaskProxyless*
```python
from capmonster_python import NoCaptchaTaskProxyless

capmonster = NoCaptchaTaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *NoCaptchaTask*
```python
from capmonster_python import NoCaptchaTask

capmonster = NoCaptchaTask(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL", proxyAddress="8.8.8.8", proxyPort=8080, proxyLogin="login", proxyPassword="password", proxyType="http or https")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *RecaptchaV3TaskProxyless*
> default minimum score: 0.3 and default page_action: verify
```python
from capmonster_python import RecaptchaV3TaskProxyless

capmonster = RecaptchaV3TaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL", minimum_score=0.7, page_action="verify")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *FunCaptchaTaskProxyless*
> default js_subdomain: None and default data_blob: None
```python
from capmonster_python import FunCaptchaTaskProxyless

capmonster = FunCaptchaTaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_url="URL", website_public_key="PUBLIC")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *FunCaptchaTask*
> default js_subdomain: None and default data_blob: None
```python
from capmonster_python import FunCaptchaTask

capmonster = FunCaptchaTask(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_url="URL", website_public_key="PUBLIC", proxyAddress="8.8.8.8", proxyPort=8080, proxyLogin="login", proxyPassword="password", proxyType="http")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *HCaptchaTaskProxyless*
```python
from capmonster_python import HCaptchaTaskProxyless

capmonster = HCaptchaTaskProxyless(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```
##### *HCaptchaTask*
```python
from capmonster_python import HCaptchaTask

capmonster = HCaptchaTask(client_key="CLIENT KEY")
taskId = capmonster.createTask(website_key="WEBSITE_KEY", website_url="URL", proxyAddress="8.8.8.8", proxyPort=8080, proxyLogin="login", proxyPassword="password", proxyType="http or https")
response = capmonster.joinTaskResult(taskId=taskId)
print(response)
```

> For detailed documentation (not this library's) is here: [capmonster.cloud documentation](https://zennolab.atlassian.net/wiki/spaces/APIS/pages/491575/English+Documentation)