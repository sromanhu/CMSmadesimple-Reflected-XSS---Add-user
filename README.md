# CMSmadesimple Reflected XSS v2.2.18

## Author: (Sergio)

**Description:** Multiple cross-site scripting (XSS) vulnerabilites in install/adduser.php of CMSmadesimple v.2.2.18 allows a local attacker to execute arbitrary code via a crafted script to the password and password again in the My Preferences - Add user.

**Attack Vectors:** Scripting a vulnerability in the sanitization of the entry in the password and password of "My Preferences - Add user." allows injecting JavaScript code that will be executed when forward the request.

---

### POC:


When logging into the panel, we will go to the "My Preferences - Add user" section off General Menu.

![XSS password fields](https://github.com/sromanhu/CMSmadesimple-Stored-XSS---Add-user/assets/87250597/ccd58b10-56e6-4414-a18a-6a93145361fe)






We edit that Content - News Menu with the payload that we have created and see that we can inject arbitrary Javascript code in the assword and password again field.


### XSS Payload:

```js
'"><svg/onload=alert('password')>
```

```js
'"><svg/onload=alert('password again')>
```


In the following image you can see the embedded code that executes the payload when forward the request.
![XSS password result1](https://github.com/sromanhu/CMSmadesimple-Stored-XSS---Add-user/assets/87250597/091d3b80-727e-47ff-b678-82867f00e9f1)

![XSS password result 2](https://github.com/sromanhu/CMSmadesimple-Stored-XSS---Add-user/assets/87250597/90304fe3-39d1-47b4-a913-cf6858717a6a)








</br>

### Additional Information:
http://www.cmsmadesimple.org/

https://owasp.org/Top10/es/A03_2021-Injection/

