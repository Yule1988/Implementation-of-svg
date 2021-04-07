---
layout: default
title: Modul FSH
has_children: true
nav_order: 4
---

****

\

FlaSH, the flasher shell
========================

Contents
--------

-   [Class Shell](#Class_Shell)

Modules
-------

-   **fsh**

Module `fsh`
============

The FlaSHer application.

A helpful tool to write, verify, read and erase data in flash.

[Class Shell](#Class_Shell)
---------------------------

  -------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------
  [Shell:\_init ()](#Shell:_init)                                                                    Initialize the Shell object.
  [Shell:\_\_getNetxPath ()](#Shell:__getNetxPath)                                                   Get the path of the Netx.
  [Shell:\_\_getFolderEntries (strFolder, strPrintPrefix, astrWords)](#Shell:__getFolderEntries)     Get the folder entries.
  [Shell:\_\_getFilenameWords (strMatch)](#Shell:__getFilenameWords)                                 Get all filename words of the directory.
  [Shell.\_\_HelpTopics\_templete](#Shell.__HelpTopics_templete)                                     A templete function as string.
  [Shell:\_\_run\_help (tCmd)](#Shell:__run_help)                                                    Show the help of the given command.
  [Shell:\_\_getBusUnitCs (strDevice)](#Shell:__getBusUnitCs)                                        Get the bus, unit and cs of the device.
  [Shell:\_\_getRange (tCmd)](#Shell:__getRange)                                                     Determine the startaddress and length of data.
  [Shell:\_\_switchToDevice (ucBus, ucUnit, ucCS)](#Shell:__switchToDevice)                          Switch to a new device or stay with the current one.
  [Shell:\_\_run\_read (tCmd)](#Shell:__run_read)                                                    \_*run*read.
  [Shell:\_\_run\_verify (tCmd)](#Shell:__run_verify)                                                \_*run*verify.
  [Shell:\_\_run\_write (tCmd)](#Shell:__run_write)                                                  \_*run*write.
  [Shell:\_\_run\_erase (tCmd)](#Shell:__run_erase)                                                  \_*run*erase.
  [Shell:\_\_run\_iserased (tCmd)](#Shell:__run_iserased)                                            \_*run*iserased.
  [Shell:\_\_str2hex (strData)](#Shell:__str2hex)                                                    \_\_str2hex.
  [Shell:\_\_run\_hash (tCmd)](#Shell:__run_hash)                                                    \_*run*hash.
  [Shell:\_\_run\_scan ()](#Shell:__run_scan)                                                        \_*run*scan.
  [Shell:\_\_run\_connect (tCmd)](#Shell:__run_connect)                                              \_*run*connect.
  [Shell:\_\_run\_disconnect ()](#Shell:__run_disconnect)                                            \_*run*disconnect.
  [Shell:\_\_run\_input (tCmd)](#Shell:__run_input)                                                  \_*run*input.
  [Shell:\_\_run\_debug (tCmd)](#Shell:__run_debug)                                                  \_*run*debug.
  [Shell:\_\_list\_replace (tListCmd, tListCmdsTemp)](#Shell:__list_replace)                         \_*list*replace.
  [Shell:\_\_list\_exchange (tListCmd, tListCmdsTemp)](#Shell:__list_exchange)                       \_*list*exchange.
  [Shell:\_\_list\_switch (tListCmd, tListCmdsTemp)](#Shell:__list_switch)                           \_*list*switch.
  [Shell:\_\_list\_insert (tListCmd, tListCmdsTemp)](#Shell:__list_insert)                           \_*list*insert.
  [Shell:\_\_list\_save (tListCmd, tListCmdsTemp)](#Shell:__list_save)                               \_*list*save.
  [Shell.strFilename](#Shell.strFilename)                                                            \_*list*replace.
  [Shell:\_\_list\_load (tListCmd, tListCmdsTemp)](#Shell:__list_load)                               \_*list*load.
  [Shell:\_\_list\_add (tListCmd, tListCmdsTemp)](#Shell:__list_add)                                 add a specified list to the current list
  [Shell:\_\_list\_run (tListCmd, tListCmdsTemp)](#Shell:__list_run)                                 process the specified interval of the list and quit the list command
  [Shell:\_\_list\_clear (tListCmd, tListCmdsTemp)](#Shell:__list_clear)                             clear the specified interval of the list
  [Shell:\_\_list\_end (tListCmd, tListCmdsTemp)](#Shell:__list_end)                                 quit the list command - save tListCmdsTemp to tListPreviousCmds - deactivate hints/words of auxiliary commands
  [Shell:\_\_list\_abort (tListCmd, tListCmdsTemp)](#Shell:__list_abort)                             quit the list command - save tListCmdsTemp to tListPreviousCmds - deactivate hints/words of auxiliary commands
  [Shell:\_\_run\_list (tCmd)](#Shell:__run_list)                                                    Description
  [Shell:\_\_run\_quit ()](#Shell:__run_quit)                                                        Description
  [Shell:\_\_getCompletions (tCompletions, strLine, astrWords, strMatch)](#Shell:__getCompletions)   Description
  [Shell:\_\_getMatchingHints (astrWords, strMatch)](#Shell:__getMatchingHints)                      Description
  [Shell:\_\_completer (tCompletions, strLine)](#Shell:__completer)                                  Description
  [Shell:\_\_hints (strLine)](#Shell:__hints)                                                        Description
  [Shell:run ()](#Shell:run)                                                                         Description
  [Shell.astrPlugins](#Shell.astrPlugins)                                                            Description
  [Shell.tShell](#Shell.tShell)                                                                      Run the shell.
  -------------------------------------------------------------------------------------------------- ----------------------------------------------------------------------------------------------------------------

\
 \

Class Shell {.section-header .has-description}
-----------

Shell class.

  **Shell:\_init ()** 
:   Initialize the Shell object.
  **Shell:\_\_getNetxPath ()** 
:   Get the path of the Netx.

    ### Returns:

  **Shell:\_\_getFolderEntries (strFolder, strPrintPrefix, astrWords)** 
:   Get the folder entries. Supports the function \_\_getFilenameWords.

    ### Parameters:

    -   strFolder directory
    -   strPrintPrefix prefix of folder
    -   astrWords table of all words in the directory

  **Shell:\_\_getFilenameWords (strMatch)** 
:   Get all filename words of the directory.

    ### Parameters:

    -   strMatch entered directory plus unfinished filename/folder

    ### Returns:

  **Shell.\_\_HelpTopics\_templete** 
:   A templete function as string. The text size of a block is set to 80
    chars.

    ### Fields:

    -   text templete of the \_*run*help function

  **Shell:\_\_run\_help (tCmd)** 
:   Show the help of the given command.

    ### Parameters:

    -   tCmd table of commands

  **Shell:\_\_getBusUnitCs (strDevice)** 
:   Get the bus, unit and cs of the device.

    ### Parameters:

    -   strDevice device ID

    ### Returns:

    1.  ucBus: number of bus
    2.  ucUnit: number of unit
    3.  ucCS: number of CS

  **Shell:\_\_getRange (tCmd)** 
:   Determine the startaddress and length of data. \
     In addition, it verifies whether the values of startaddress, length
    and endadress are within the range of the device

    ### Parameters:

    -   tCmd table of commands

    ### Returns:

    1.  ulStart: startaddress
    2.  ulLength: length of data

  **Shell:\_\_switchToDevice (ucBus, ucUnit, ucCS)** 
:   Switch to a new device or stay with the current one.

    ### Parameters:

    -   ucBus number of bus
    -   ucUnit number of unit
    -   ucCS number of cs

    ### Returns:

  **Shell:\_\_run\_read (tCmd)** 
:   \_*run*read. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_verify (tCmd)** 
:   \_*run*verify. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_write (tCmd)** 
:   \_*run*write. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_erase (tCmd)** 
:   \_*run*erase. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_iserased (tCmd)** 
:   \_*run*iserased. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_str2hex (strData)** 
:   \_\_str2hex. Return the input String as Hex value

    ### Parameters:

    -   strData one of the magic characters '.' represents any single
        character

  **Shell:\_\_run\_hash (tCmd)** 
:   \_*run*hash. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_scan ()** 
:   \_*run*scan. Some description
  **Shell:\_\_run\_connect (tCmd)** 
:   \_*run*connect. Some description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_disconnect ()** 
:   \_*run*disconnect. Some description
  **Shell:\_\_run\_input (tCmd)** 
:   \_*run*input. reads the specified input file and verify whether each
    line is a valid command

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_debug (tCmd)** 
:   \_*run*debug. display or save all debug information

    ### Parameters:

    -   tCmd

  **Shell:\_\_list\_replace (tListCmd, tListCmdsTemp)** 
:   \_*list*replace. activate the replace command - the subsequent
    command replaces a command at the specified position

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_exchange (tListCmd, tListCmdsTemp)** 
:   \_*list*exchange. exchange the position of two commands

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_switch (tListCmd, tListCmdsTemp)** 
:   \_*list*switch. switch the position of one command

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_insert (tListCmd, tListCmdsTemp)** 
:   \_*list*insert. activate the insert command - the subsequent command
    is insert at the specified position

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_save (tListCmd, tListCmdsTemp)** 
:   \_*list*save. save the current list to the given filename

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell.strFilename** 
:   \_*list*replace. save the list to the given filename
  **Shell:\_\_list\_load (tListCmd, tListCmdsTemp)** 
:   \_*list*load. load a specified list - overwrite the current list

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_add (tListCmd, tListCmdsTemp)** 
:   add a specified list to the current list

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_run (tListCmd, tListCmdsTemp)** 
:   process the specified interval of the list and quit the list command

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_clear (tListCmd, tListCmdsTemp)** 
:   clear the specified interval of the list

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_end (tListCmd, tListCmdsTemp)** 
:   quit the list command - save tListCmdsTemp to tListPreviousCmds -
    deactivate hints/words of auxiliary commands

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_list\_abort (tListCmd, tListCmdsTemp)** 
:   quit the list command - save tListCmdsTemp to tListPreviousCmds -
    deactivate hints/words of auxiliary commands

    ### Parameters:

    -   tListCmd
    -   tListCmdsTemp

  **Shell:\_\_run\_list (tCmd)** 
:   Description

    ### Parameters:

    -   tCmd

  **Shell:\_\_run\_quit ()** 
:   Description
  **Shell:\_\_getCompletions (tCompletions, strLine, astrWords, strMatch)** 
:   Description

    ### Parameters:

    -   tCompletions
    -   strLine
    -   astrWords
    -   strMatch

  **Shell:\_\_getMatchingHints (astrWords, strMatch)** 
:   Description

    ### Parameters:

    -   astrWords
    -   strMatch

  **Shell:\_\_completer (tCompletions, strLine)** 
:   Description

    ### Parameters:

    -   tCompletions
    -   strLine

  **Shell:\_\_hints (strLine)** 
:   Description

    ### Parameters:

    -   strLine

  **Shell:run ()** 
:   Description
  **Shell.astrPlugins** 
:   Description

    ### Fields:

    -   romloader\_eth
    -   romloader\_usb
    -   romloader\_uart
    -   romloader\_jtag

  **Shell.tShell** 
:   Run the shell.

*generated by [LDoc 1.4.6](http://github.com/stevedonovan/LDoc)* *Last
updated 2021-04-07 21:54:29*
