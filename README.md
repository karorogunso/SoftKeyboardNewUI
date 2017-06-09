# SoftKeyboardNewUI
The soft keyboard engine provides a software keyboard allows the user to input text by clicking on the keys displayed on the screen. 

The framework supports input of the alphabet, special characters, symbols, and even characters from other languages (as long as the font allows for it) into any Ren'Py game.  

By UnicornStudiosOsaka (AKA. Aoide) 

But Port to Use New UI for Renpy 6.99.12.4.2187+
by KimoiEngineGuy

Installation

Unzip the framework archive and copy the contents into your Ren'Py game folder.

To use the software keyboard, you need to call the input screen:

call screen input_softkeyboard
Archive contents
softkeyboard - this folder contains the SoftKeyboard code
common.rpy - this file contains the SoftKeyboard screens that are common to all languages
en.rpy - this file contains the English specific screens and variables
jp.rpy - this file contains the Japanese specific screens and variables
softkeyboard.rpy - this file contains the functions necessary for SoftKeyboard to work
lang - this folder contains the language support files
jp - this folder contains the files necessary for running Ren'Py in Japanese
defaults.rpy - this file contains any default values necessary for mufti-lingual support
language.rpy - this file contains the necessary code for mufti-lingual support
Multilingual support

Softkeyboard jp.jpg

By default SoftKeyboard supports both English and Japanese. The language files are contained in the lang folder and are based on the Multiple Language Support Cookbook entry.

Switching between languages
The easiest way to give the user the option to choose the language they want to play the game in is to add the following code to the main menu screen:

textbutton _("Language") action ShowMenu("language_picker")
Forcing only one language
If you wish to force only one language, open lang/language.rpy and find:

init -101 python:
    if persistent.lang is None:
        persistent.lang = DEFAULT_LANG
        persistent.chose_lang = False    
    lang = persistent.lang  
Change persistent.chose_lang = False to persistent.chose_lang = True.

For non-English games, open lang/defaults.rpy and change DEFAULT_LANG to the appropriate language.


Note: If you set the default language to anything other than "en" or "jp" you will need to create and add the appropriate language file in the softkeyboard folder!
