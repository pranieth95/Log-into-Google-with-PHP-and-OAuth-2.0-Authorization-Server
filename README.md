# SSS-Assignment-3
<submission>
    <regno>IT16145344</regno>
    <name>Chandrasekara CMSPK</name>
    <email>praniethkumara@gmail.com</email>
</submission>
Step 1: Enable the Google+ API
Create a Google API Console project, OAuth 2.0 client ID, and register your JavaScript origins:
1.	Go to the Google API Console 
2.	From the project drop-down, select an existing project, or create a new one by selecting Create a new project. 
Note: Use a single project to hold all platform instances of your app (Android, iOS, web, etc.), each with a different Client ID. 
3.	Enable the Google+ API service: 
1.	In the list of Google APIs, search for the Google+ API service.
2.	Select Google+ API from the results list.
3.	Press the Enable API button. Wait for the API to be enabled.
This action adds the service to the Enabled APIs tab, which you can access by selecting APIs & Services on the left menu. You can turn off the Google Cloud services. 
4.	In the sidebar under "APIs & Services", select Credentials, then select the OAuth consent screen tab. 
1.	Choose an Email Address, specify a Product Name, and press Save. 
5.	In the Credentials tab, select the New credentials drop-down list, and choose OAuth client ID.
6.	Under Application type, select Web application. 
Register the origins from which your app is allowed to access the Google APIs, as follows. An origin is a unique combination of protocol, hostname, and port. 
1.	In the Authorized JavaScript origins field, enter the origin for your app. You can enter multiple origins to allow for your app to run on different protocols, domains, or subdomains. You cannot use wildcards. The Authorized redirect URI field does not require a value. Redirect URIs are not used with JavaScript APIs. 
2.	Press the Create button. 
7.	From the resulting OAuth client dialog box, copy the Client ID and Client secret. The Client ID lets your app access enabled Google APIs. 
Step 2: Set up the PHP quick-start app
1.	Get the latest version of the quick-start.  download the application as a zip file, and extract the library and quick-start code:
2.	If you are not using PHP's built-in web server, move the quick-start app directory to a location that your web server can host files, for example:
mv gplus-quickstart-php /var/www
3.	Change to the directory where the quick-start app is located.
cd gplus-quickstart-php
4.	Edit signin.php, and replace YOUR_CLIENT_ID and YOUR_CLIENT_SECRET with the values that you generated in Step 1.
5.	Install Composer:
curl -s https://getcomposer.org/installer | php
6.	Execute composer to install the quick-start dependencies:
php composer.phar install
Step 3: Run the quick-start app
After you set up your Google API Console project and configured the quick-start app, the app is ready to run.
Because you registered http://localhost:4567 as a Web origin in the Google API Console, you will run the sample from that location.
•	If you are using the built-in PHP web server, start it with the following command:
php -S localhost:4567
Next, browse to your quick-start app, loading signin.php from the URL where you hosted it:
http://localhost:4567/signin.php
•	If you are using another web server, make sure to set permissions on the files in the folder to include execute permissions for signin.php and read permissions for the required libraries.
chmod +x /var/www/gplus-quickstart-php/signin.php
chmod -R 555 /var/www/gplus-quickstart-php/vendor
Next, browse to your quick-start app, loading signin.php from the URL where you hosted it:
http://localhost:4567/gplus-quickstart-php/signin.php
After you sign in, the application uses the JavaScript client to retrieve your profile and uses the PHP client library to retrieve the people visible to the app.
Clicking Disconnect from Google+ results in the server making a call to Google to revoke the refresh token. The server then removes any data that it acquired from Google about the user to disconnect the app and follow the developer policies.

