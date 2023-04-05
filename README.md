Package Name: MW_API_Parser
Author: Jerry White
Package URL: https://github.com/whitej27030/mw_api_parser.git

Built using: Merriam-Webster API - https://DictionaryAPI.com

This repository contains scripts which allow you to access definitions, audio pronunciation and more from Merriam-Webster's online dictionary. 

## Getting Started

These instructions will get you a copy of the project up and running on your local machine for development and testing purposes.

### Prerequisites

*This package MUST be installed on Python versions 3.11 or later*

You will also need to visit:"https://www.dictionaryapi.com/". Click on "Dev Center" and sign-up. Make sure you make note of your API keys as you will need them later. 

Next, you will need to create a `.env` file. This file should contain the reference work you will contact with this script and your Merriam-Webster API key. There is a "Sample_Env.txt" file in the project directory that you can use as a template. You can rename this file to ".env" (without the quotes), and place your Merriam-Webster API Key where noted. The current version will only work properly with the "collegiate" reference API, so this line should not be modified. 

 If you would rather keep the .env file in another location, you can set an environment variable named "MW_API_PARSER_CONFIG" (again, without the quotes), using the commands for your operating system below:

First, open a command line session on your given OS, then:

 - On Linux /  Mac OS:
export MW_API_PARSER_CONFIG=/Path_To_Folder_Containing_Env_File/
Make sure you include the '/' at the end of the path!
 - On Windows:
setx MW_API_PARSER_CONFIG "c:/<Path_To_Folder_Containing_Env_File/"

Make sure you put the '/' at the end of the folder path!

Also note that the Windows `setx` command only adds the environment variable to the current session. To set this variable globally, the command will need to be ran with Administrator rights.

### Installing

Clone or download this repository to your local machine. You can also install from PyPI with the following command:

    'pip install mw_api_parser'

## Scripts

### MW_Response

This first script will retrieve the definition for the word passed into the function. In this case, the word passed in is "jaded".

```
from mw_api_parser import MW_Response

response = MW_Response('jaded')
```

### Build_Audio_Links

This script will create a list of audio links for the word passed in.

```
from mw_api_parser import Build_Audio_Links

links = Build_Audio_Links(test1)

print(type(links))

for x in range(0, len(links)):
    print(links[x])
```

### Get_Def_HTML

This script will return a list of HTML code containing the definition for the word passed in.

```
from mw_api_parser import Get_Def_HTML

html_response = Get_Def_HTML(test1)

print(type(html_response))

for x in range(0, len(html_response + '\n'))
    print(html_response[x])
```

### Get_Def_Original

This script will return a list containing the original definition for the word passed in.

```
from mw_api_parser import Get_Def_Original

orig_response = Get_Def_Original(test1)

print(type(orig_response))

for x in range(0, len(orig_response)):
    print(orig_response[x] + '\n')
```

### Get_Def_Plain_Text

This script will return a list containing the plain text definition for the word passed in.

```
from mw_api_parser import Get_Def_Plain_Text

plain_text = Get_Def_Plain_Text(test2)

print(type(plain_text))

for x in range(0, len(plain_text)):
    print(plain_text[x])
```
