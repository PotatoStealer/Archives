# Going Postal

Who doesn't like getting packages?

### Problem Description
``````
A new delivery service is in town, but the site doesn't seem to be fully complete. Maybe there's a secret administrative interface that we can access somehow?
``````

<img src="https://github.com/PotatoStealer/Archives/blob/master/WhiteHacks2020/Going%20Postal/website.PNG" style="zoom: 40%"/> 

This is a reference to the GET and POST requests.

Sending a GET request to `http://chals.whitehacks.ctf.sg:13001`:
``````css
...
            <li><a href="#" class="nav-link">Testimonials</a></li>
            <li><a href="#" class="nav-link">About</a></li>

            <!-- 
                    PLEASE REMOVE FROM PRODUCTION 
                    **Update: 15/07/2020 - removed GET endpoint! I don't think there's any other method of getting in, so gonna leave this here for now.

                    <li><a href="/admin_s3kr1t_backd0Or" class="nav-link">Admin</a></li>
                    
            -->
``````

The comment seems to hint at some hidden directory, indicated by the `href` tag. Let's append that to the back of the given URL.
We can't use GET requests since the endpoint has been removed. This calls for a POSTman!

Sending a POST request to the new URL `http://chals.whitehacks.ctf.sg:13001/admin_s3kr1t_backd0Or` gives `WH2020{POST4l_s3rv1ces}`.
