# voice-intents
yaml code I've created/re-purposed for voice control in Home Assistant since the 2023.7 update brought voice control to android &amp; WearOS

Getting started :

Add this line to configuration.yaml :-

intent_script: !include config_assist_intent_script.yaml

This tells HA that your intent scripts will be in a different file, with that name. Copy the file from my repo to your filesystem under /config

All the other files need to be copied to :- /config/custom_sentences/en - if you are using english as your HA language. Adjust to a diffent lang code if you are not (I've not tested this, sorry)



Setting Timers
==============

Taken from https://community.home-assistant.io/t/set-a-timer-using-ha-assist - credit to the guys on that thread :)

Note - you need to create 3 timers (in helpers) and you also need to create automations for then the timer expires. As well as starting/stopping timers, you can ask how long is left.

Adding to shopping list
=======================

This is no longer needed since 2023.8

~~Taken from https://community.home-assistant.io/t/calling-shopping-list-add-item-service-from-ha-assist/540427 - credit to the guys on that thread :)~~

~~Note, that currently you need to prepopulate the list with the items you ever want to add (which is a pain, although I used some python to create the yaml)~~
~~My plan is to set up https://github.com/siemon-geeroms/yarvis - but I've not got it working yet~~

Person finder
=============

Taken from https://community.home-assistant.io/t/custom-intents-using-name/571831 - credit to the guys on that thread :)

You can ask : "Is person X at home?" "Where is person X ?"  - Needs https://www.home-assistant.io/integrations/google_maps/ for location tracking (or companion app on all phones)

Washing machine timer checker
=============================

Since I have the Bosch integration on my washing machine, it provides a 'time left on cycle' value. You can query this (with optional swearing) 

Setting reminders
=================

Create a helper called input_text.reminder and create a dashboard entry to display it. You can then say stuff like : "Create a reminder to post that letter"
