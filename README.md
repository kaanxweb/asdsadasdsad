## How to obtain the credentials to communicate with Google Analytics

### Getting credentials

The first thing you’ll need to do is to get some credentials to use Google API’s. I’m assuming that you’ve already created a Google account and are signed in. Head over to [Google API’s site](https://console.developers.google.com/apis) and select or create a project.

![1](https://spatie.github.io/laravel-analytics/v5/1.png)

Next up we must specify which API’s the project may consume. Go to the API Library and search for "Google Analytics Data API".

![2](https://spatie.github.io/laravel-analytics/v5/2.png)
![3](https://spatie.github.io/laravel-analytics/v5/3.png)

Choose enable to enable the API.
![4](https://spatie.github.io/laravel-analytics/v5/4.png)

Now that you’ve created a project that has access to the Analytics API it’s time to download a file with these credentials. Click "Credentials" in the sidebar. You’ll want to create a "Service account key".
![5](https://spatie.github.io/laravel-analytics/v5/5.png)

On the next screen you can give the service account a name. You can name it anything you’d like. In the service account id you’ll see an email address. We’ll use this email address later on in this guide.

![6](https://spatie.github.io/laravel-analytics/v5/6.png)

Go to the details screen of your created service account and select "keys", from the "Add key" dropdown select "Create new key". 

![7](https://spatie.github.io/laravel-analytics/v5/7.png)

Select "JSON" as the key type and click "Create" to download the JSON file.

![8](https://spatie.github.io/laravel-analytics/v5/8.png)

Save the json inside your Laravel project at the location specified in the `service_account_credentials_json` key of the config file of this package. Because the json file contains potentially sensitive information I don't recommend committing it to your git repository.

### Granting permissions to your Analytics property

I'm assuming that you've already created a Analytics account on the [Analytics site](https://analytics.google.com/analytics) and are using the new GA4 properties.

First you will need to know your property ID. In Analytics, go to Settings > Property Settings. Here you will be able to copy your property ID. Use this value for the `ANALYTICS_PROPERTY_ID` key in your .env file.

![a1](https://spatie.github.io/laravel-analytics/v5/a1.png)

Now we will need to give access to the service account you created. Go to "Property Access Management" in the Admin-section of the property.
Click the plus sign in the top right corner to add a new user.

On this screen you can grant access to the email address found in the `client_email` key from the json file you download in the previous step. Analyst role is enough.

![a2](https://spatie.github.io/laravel-analytics/v5/a2.png)