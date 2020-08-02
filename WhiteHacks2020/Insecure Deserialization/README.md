# GovTech SecTech(3/6) - Insecure Deserialization

Because cookies are for rookies

### Problem Description
``````
GovTech Sponsor Challenge

Trusting serialized data without verification them can be precarious. To this end, we ask that you be like the Cookie Monster, attentive and inquisitive.   
``````
The description strongly suggests that we analyze the cookies involved.
 
<img src="https://github.com/PotatoStealer/Archive/blob/master/Whitehacks2020/Insecure%20Deserialization/cookie.png" style="zoom: 40%"/> 

The cookie named `sectech` seems to be important; with value `YToyOntzOjQ6InVzZXIiO3M6ODoidGVtcF9hY2MiO3M6NToiYWRtaW4iO2I6MDt9`.
This is a Base64 string, which upon decoding gives `a:2:{s:4:"user";s:8:"temp_acc";s:5:"admin";b:0;}`.

In particular, the `admin` property is associated with the value 0(for false). This motivates us to set it to 1(for true).
Modifying the value and re-encoding to Base64 gives `YToyOntzOjQ6InVzZXIiO3M6ODoidGVtcF9hY2MiO3M6NToiYWRtaW4iO2I6MTt9`. 

Replacing the original cookie with our new and improved cookie works like a charm, as with all cookies! Let's send it back.

<img src="https://github.com/PotatoStealer/Archive/blob/master/Whitehacks2020/Insecure%20Deserialization/success.png" style="zoom: 40%"/>

The flag is `WH2020{Cook!3Ins3cur3Des3r!al!zat!on_Adm!nR!ghts}`.
