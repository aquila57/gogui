# gogui
Two JAR files for gogui

## License

The original license for the gogui project at Sourceforge
applies to the JAR files in this repository.

## History

Gogui is an obsolete project on Sourceforge.
The original author for gogui no longer maintains the project, and
no one has volunteered to maintain the project on Sourceforge.
Remi Coulom has made some enhancements to gogui.

## Reason for this repository

Sourceforge no nonger contains a compiled version of gogui.
Therefore this repository contains two programs from
the Sourceforge project, as JAR files.  These are the two
JAR files in the gogui project, that I use every day.

gogui.jar - play Go against a Go engine, using the GTP protocol.

gogui-twogtp.jar - play two Go engines against each other,
using the GTP protocol.

# gogui.jar

gogui.jar is a Go client program using the GTP protocol.
I use gogui to play against Leela Zero.  You should be able
to use gogui to play against Katago, as well.

# gogui-twogtp.jar

gogui-twogtp.jar is a console program to play two Go engines
against each other.  I use gogui-twogtp.jar to play Leela Zero
against itself.  You can also use this program to play Katago
against itself.  With this program, you can have two log files
as output, one log file for each Go engine.  When playing Leela
Zero against itself, each log file tells you what the play-outs
are for each move.

# References

Senseis's library (wiki) has references to gogui and Remi Coulom.

https://senseis.xmp.net/?Gogui - Description of the gogui program.

https://senseis.xmp.net/?RemiCoulom - brief bio about Remi Coulom.

# Usage

java -jar gogui.jar

java -jar gogui-twogtp.jar [options]

# Example

Example of running gogui-twogtp.jar with options:


\#!/bin/bash

#########################################################

\# I run java from the jdk

#########################################################

PATH=$JAVAPATH/java/jdk1.8.0_301/bin:$PATH

export PATH

#########################################################

\# example of how to get help with gogui-twogtp

#########################################################

 # java -jar gogui-twogtp.jar -help

 # exit 0

#########################################################

 # Explanation of options:

 # -auto runs the program automatically

 # -games 1 runs the program for only one game

 # -sgffile prefix for the SGF output file

 # -komi 7.5 means default to 7.5 komi.

 # -size 19 means play on 19x19 board

 # -threads 1 means use one thread per engine

 # -verbose means print verbose output

 # -black "Go engine program and options for black"

 # -white "Go engine program and options for white"

 # The Go program and options for each Go engine must be

 # enclosed in double quotes.

 # Go options I use for each engine of Leela Zero:

 # -g means use the GTP protocol

 # -r 1 means resign at 1% probability of winning, or less

 # -t 1 means use only one thread

 # -l log path with log name

 # -w weights path with weights name (in gzip format)

#########################################################

java -jar gogui-twogtp.jar \

-auto \

-games 1 \

-black "$LZPATH/leelaz \

-g -r 1 -t 1 \

-l $LOGPATH/logb \

-w $WEIGHTPATH/wt287.gz" \

-white "$LZPATH/leelaz \

-g -r 1 -t 1 \

-l $LOGPATH/logw \

-w $WEIGHTPATH/wt287.gz" \

-komi 7.5 \

-sgffile two \

-size 19 \

-threads 1 \

-verbose

##################################################################

End of example

##################################################################
