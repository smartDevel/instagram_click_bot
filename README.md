# instagram_click_bot
<h1>Generate more traffic on Instagram account with simple python program</h1>
You’ll need Python (I’m using Python 3.7), Selenium, a browser (e.g. Chrome) and… obviously, an Instagram account! Quick overview regarding what the bot will do:
<ul>
  <li>    Open a browser and login with your credentials</li>
  <li>    For every hashtag in the hashtag list, it will open the page and click the first picture to open it</li>
  <li>    It will then like, follow, comment and move to the next picture, in a 200 iterations loop (number can be adjusted)</li>
  <li>    Saves a list with all the users you followed using the bot</li>
</ul>
In order to use chrome with Selenium, you need to install chromedriver. It’s a fairly simple process and I had no issues with it. Simply install and replace the path above. Once you do that, our variable webdriver will be our Chrome tab.

In cell number 3 you should replace the strings with your own username and the respective password. This is for the bot to type it in the fields displayed. You might have already noticed that when running cell number 2, Chrome opened a new tab. After the password, I’ll define the login button as an object, and in the following line, I click it.

If you’re wondering what those weird strings are, don’t be scared! On my article about web scraping a real estate website, I’ve been through a similar task, which consisted in inspecting the web pages in order to tell the bot where to look. You can do that very easily, simply by right clicking the element you want to map, and selecting Inspect.

Once you get in inspect mode find the bit of html code that corresponds to what you want to map. Right click it and hover over Copy. You will see that you have some options regarding how you want it to be copied. I used a mix of XPath and css selectors throughout the code (it’s visible in the find_element_ method). It took me a while to get all the references to run smoothly. At points, the css or the xpath directions would fail, but as I adjusted the sleep times, everything started running smoothly.

In this case, I selected “copy selector” and pasted it inside a find_element_ method (cell number 3). It will get you the first result it finds. If it was find_elements_, all elements would be retrieved and you could specify which to get.

Once you get that done, time for the loop. You can add more hashtags in the hashtag_list. If you run it for the first time, you still don’t have a file with the users you followed, so you can simply create prev_user_list as an empty list.

Once you run it once, it will save a csv file with a timestamp with the users it followed. That file will serve as the prev_user_list on your second run. Simple and easy to keep track of what the bot does.

Update with the latest timestamp on the following runs and you get yourself a series of csv backlogs for every run of the bot.
