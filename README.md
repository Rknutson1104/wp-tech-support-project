# wp-tech-support-project
WordPress Technical Customer Support test

## Issue 1 - Answer

This is how we need to clear your cache at a specific time. 

First, make sure that you install the Disabling the Automatic Chache Clearing plugin:  [wp-rocket-no-cache-auto-purge.zip](https://github.com/Rknutson1104/wp-tech-support-project/files/7086876/wp-rocket-no-cache-auto-purge.zip). 

Second, go to the WP Rocket settings and click on Cache, then Cache Lifespan and set that to 0.

Third, you want to save your server resources by disabling **WP_CRON** and inserting the following code in your **wp-config.php** file before the "/*Happy publishing*/" line:

define(DISABLE_WP_CRON', true);

Fourth, download this PHP file [wp_rocket_clear_cache.zip](https://github.com/Rknutson1104/wp-tech-support-project/files/7086893/wp_rocket_clear_cache.zip) and upload it to your root directory where the **wp-config.php** and **wp-load.php** files are located.

Fifth, we need to set up a cron job in order to manually clear the cache at a specific time each day. Each server is different so if you are not sure how to do this, contact your hosting provider. 

Now, set the custom time and use this command below to clear the WP Rocket Cache at the time you wish to clear it (make sure you replace example.com with your website name).

**wget -g -O - https://example.com/rocket-clear-cache.php >/dev/null 2&1**


## Issue 2 - Answer

I would double check their site/server that they entered everything correctly and did not miss anything, i.e., a semicolon or parentheses. That can be done very easily with everyone, which probably happend.

I would also try to test the PHP file by loading it to check if the cache is cleared:

**https://example.com/rocket-clear-cache.php**

If the cache is cleared, we can confirm the PHP file is not the culprit and a cron job misconfiguratin could be causing the issue.

We then would need to check the cron job log files, see if it is running, and check if the job was created.


