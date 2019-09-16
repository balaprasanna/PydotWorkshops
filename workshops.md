# Module 0

- Foundational Python refresher...
- *Please refer to this notebook * for more info
  - ```Module 0 - Python foundation workshop.ipynb``` 
  or
  - The online version https://colab.research.google.com/drive/1zODEZjSyCbdD-WrMwrJrd5h3c3M3D498



# Module 1:
- Basic Python
    - Loops, Dict, functions, Packages
- Read & Write Text files
    - Csv file, Text file
    - Loop inside a Folder
- explore some packages
    
---    

Scenario
---

1. You have been given a file (text file + zip file).
2. `Readme.md` Read this file for more info on the task /workshop
3. Write a python program to finish the task
4. Packages to use will be listed in requirements.txt
*Feel free to add anymore packages if you wish to use.*


# Module 2:
Make API call
- Collect data from API &amp; store in csv
- Scrape static websites &amp; store in csv
---
Scenario
---

1. You have been given a API with api documentation.
2. Make api call from python & store the resp in a python dict
2. (2A) *Optional*: Store the resp dict into a file (json)

3. Parse the following info from the API Response.

Example: URL 

https://min-api.cryptocompare.com/data/price?fsym=USD&tsyms=JPY,INR
```
{
"JPY": 107.93,
"INR": 84.82
}
```
4. Store that parsed infomation/data into a csv file.

| sno | from_symbol | to_symbol | price | datetime |
| ---  | ---  | ---  | ---  | --- |
| 1 | USD | INR | 71 | ... |
| 2 | USD | SGD | 1.37| ... |

use python `time` or `datetime` module to get the current time, when you make api call and store that into the csv file..


## Part 2: Scrape static websites


https://www.xe.com/currencyconverter/convert/?Amount=1&From=USD&To=SGD


![https://i.imgur.com/C4Eub9d.png](https://i.imgur.com/C4Eub9d.png)



Have a look at the html as well, to parse the exchange rate.

![https://i.imgur.com/vDAntcv.png](https://i.imgur.com/vDAntcv.png)

1. Look at the query parameter and decide how to pass inputs..
2. Use `bs4` library to parse the html as show below.
3. You have to extract the price shown here and save it into a csv file..

| sno | from_symbol | to_symbol | price | datetime |
| ---  | ---  | ---  | ---  | --- |
| 1 | USD | SGD | 1.37| ... |

--- 


** Try this if you completed the base workshop **
---
1. Store the same data into mongodb as well
  - create a `exchange` db in your mlab account.
  - create a collection `exchange-rates`
  - You can store sample record which looks like the following json.

```
{
    "from_symbol": "USD",
    'to_symbol' : "SGD",
    "price" : 1.37,
    "datetime" : "...."
}
```


# Module 3:
-
- Pick / Choose a dataset
- Load , clean, analyze and visualize the data
---
## Scenario
- You have been given a csv file (Google playstore apps datasets..)
https://chukmunnlee.github.io/dataset/googleplaystore.csv
- Use pandas to load the data
  - Do data clean if necessary
  - Do an exploratory data analysis (Visualize different columns )
  - Get summary stats...

  - Analyze the dataset and answer the following questions with appropriate visualization technique
    - *Please see the Google Playstore Q/A Notebook for more info...*

# Module 4:
- Build a Chatbot using Telegram
---
## Scenario
- You have a build a telegram chatbot to help users to find exchnage rates...
- Refer to Module 2 workshop for this ..
- Create a telegram chatbot with your `<name>_bot`

### Bot commands

- /exchange-rate `<USD>` `<INR>`
    - Expected Response:
    - This should tell the exchange rate for USD to INR

- /exchange-rate `<USD> <INR>,<SGD>`
    - Expected Response:
    - Same as the previous one, but multiple outputs (INR and SGD)

- *Optional Features*
  
  - /list-all-symbols
    - Expected Response:
    - This should list all the available symbols.

  - /compare `<USD> <INR>,<SGD>`
    - Expected Response:
    - This should be able to plot a bar chart with values for INR , SGD and send the attachment / Image back to the user