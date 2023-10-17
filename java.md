#!/bin/sh
echo "-----------------------------------"
echo "Checking to see if \e[96mJava\e[0m is \e[32mrunning!\e[0m" 
echo "-----------------------------------"
sleep 3
if pgrep -x "java" > /dev/null
then
    echo "-----------------------------------"
    echo "\e[96mJava\e[0m is \e[32mrunning:\e[0m Attempting To Kill"
    echo "-----------------------------------"
    sleep 2
    killall SGKILL java
else
    echo "------------------------------------"
    echo "\e[96mJava\e[0m Detection \e[91mFailed:\e[0m Ending Script"
    echo "------------------------------------"
    sleep 1
    exit
fi
sleep 1
if pgrep -x "java" > /dev/null
then
    echo "-----------------------------------------"
    echo "Could not kill \e[96mJava\e[0m, Are you a \e[31mSudo User?\e[0m"
    echo "-----------------------------------------"
    sleep 2
else
    echo "------------------------------"
    echo "\e[96mJava\e[0m was killed \e[32mSuccsessfully!\e[0m"
    echo "------------------------------"
    exit
fi


#Created By Nocturnal_Toker 
