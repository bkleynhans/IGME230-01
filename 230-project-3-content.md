# Project 3 - Sprite-based Game or Experience (Roof Breaker - The Breakout Adaptation Using Physics)
## Summary
The LangIdentiLator is a web front-end that does language detection, translation and provides general information about the language you are translating to.  You enter a string in the indicated field, after which it provides you with the flag of the country that has the most people speaking the language, and it provides you with the name of the country.  It also provides a list of all the countries in the world that use this language on the bottom of the page.  You can then go and select a language to translate your text to from the dropdown list.  The translation is performed and you are provided with the translation, the flag of the destination language's country and some statistics about the country.

2 API's were used in the making of this site using 5 API queries based on input made by the user.

# Table of Contents
=================

<!--ts-->
   * [Project 2 - Web Service Application](#project-2-web-service-application)
       * [Summary](#summary)
   * [Table of Contents](#table-of-contents)
   * [Proposal](#proposal)
       * [High Concept](#high-concept)       
       * [Premise](#premise)
   * [Final Product](#final-product)
       * [Detailed Overview](#detailed-overview)           
       * [API's Used](#apis-used)
           * [REST Countries](#rest-countries)
           * [Yandex Translate](#yandex-translate)           
       * [About The Developer](#about-the-developer)
   * [Documentation](#documentation)       
       * [Resources Used](#resources-used)
       * [Project Requirements Met](#project-requirements-met)
           * [Functionality](#functionality)
           * [Design and Interaction](#design-and-interaction)
           * [HTML CSS Media](#html-css-media)
           * [Code](#code)
           * [Above and Beyond](#above-and-beyond)
   * [Grade](#grade)
<!--te-->

# Proposal
## High Concept
Create a website that uses an API to provide some sort of data.

## Premise
The original idea was to create a text translation website.  You would enter a word or phraze and the site would provide you with a translation thereof.  During the development process however, I noticed that I could expand on this concept by providing the user with additional information.  This is also where the name of the site "LangIdentiLator" was born.

# Final Product
## Detailed Overview
Once you enter a word or text into the "LangIdentiLator" it sends the text to the Yandex.Translate API.  The API then returns the two letter ISO 639-1 language code.  This code is used to send a query to the REST API, which provides a list of all the countries that have the provided language as their first language.

The array of countries is sorted by number of people in the country, with the country that has the highest population number being chosen as the primary user of the language.  Once the "country of most use" is identified, we extract a link to the country flag to display the associated flag and a description of where it is most used.

We send a query to the Yandex API to determine what languages the provided language can be translated to and then populate the dropdown box with the list of languages.  We also display a table at the bottom of the page that has quantity limits, can be sorted and searched through, that contains all the countries that have people who can speak the language which was entered by user.

At this point the user selects a language to translate to from the the dropdown list which is sent to the Yandex translation API to translate.  We also extract the flag and some additional country information from the REST API to display.

## API's Used
### REST Countries
[REST Countries](https://restcountries.eu/ "REST Countries") is a RESTful API that provides information about all countries around the world.  It is provided under the [Mozilla Public License MPL 2.0](https://www.mozilla.org/en-US/MPL/2.0/ "MPL 2.0").

### Yandex Translate
[Yandex.Translate](https://tech.yandex.com/translate/ "Yandex Translate") is a machine translation service that does language detection and translation.  It is provided under a very complex set of legal documents, but is free to use up to a maximum of 1million characters per day for a non-commercial application [Yandex Legal](https://yandex.com/legal/translate_api/ "Yandex Legal").

## About The Developer
Benjamin Kleynhans is doing his Game Design and Development major. While design is part of the major, it is not something that he wants to do. He is a programmer at heart and is more than happy making someone elses vision a reality.

To learn more about Benjamin, click on [About Benjamin Kleynhans](https://people.rit.edu/bxk8027/230/index.html "Site Home") to be directed to his homepage.

# Documentation
## Resources Used
Multiple different resources were used including:

[Yandex.Translate](https://tech.yandex.com/translate/ "Yandex Translate")
[REST Countries](https://restcountries.eu "REST Countries")
[Datatables.net](https://datatables.net "Datatables.net")
[Stackoverflow (Chaos)](https://stackoverflow.com/questions/807878/javascript-that-executes-after-page-load "Stackoverflow (Chaos)")
[Sitepoint](https://www.sitepoint.com/sort-an-array-of-objects-in-javascript/ "Sitepoint")

## Project Requirements Met
### Functionality
The program is useful, especially to travellers.
It demonstrates all the creativity I have (it took me a full day just to figure out what it should look like).
The page runs without errors.
It remembers your last translation.
It has  2 textareas (one editable and one not), 1 combobox (auto populated based on text input from textareas), a table with sort, search and filter functionality as well as page selection at the bottom of the table.

### Design and Interaction
Contains a pleasing design.
Interfaces is clear and labeled (hover as well as in-control text).
Standard interface conventions followed.
The state of the page is always obvious.
Does not throw any errors (everything is handled internally).

### HTML CSS Media
There are no HTML or CSS validation errors.
All static CSS is in an external .css file in the css directory.
All tags are used appropriately however there are some limitations due to the use of the skeleton framework which requires all content to be in divs.

### Code
All code is well structured and formatted
All code is in an external .js file in the js directory.
All code follows coding standards.

### Above and beyond
I use two APIs to get additional information to provide the user.
There are multiple controls on the page (text boxes, text areas, buttons, filtered and non-filtered combo boxes, sort buttons, linked pages, hyperlinks and page animations)

# Grade
I believe I deserve full credit (and extra credit if available) for this project.  I spent more than 40 hours working on this until 2am in the morning for multiple days.
