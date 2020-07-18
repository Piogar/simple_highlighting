```
                           _                 _                              ~
                       ___(_)_ __ ___  _ __ | | ___                         ~
                      / __| | '_ ` _ \| '_ \| |/ _ \                        ~
                      \__ \ | | | | | | |_) | |  __/                        ~
                      |___/_|_| |_| |_| .__/|_|\___|                        ~
                                      |_|                                   ~
           _     _       _     _ _       _     _   _                        ~
          | |__ (_) __ _| |__ | (_) __ _| |__ | |_(_)_ __   __ _            ~
          | '_ \| |/ _` | '_ \| | |/ _` | '_ \| __| | '_ \ / _` |           ~
          | | | | | (_| | | | | | | (_| | | | | |_| | | | | (_| |           ~
          |_| |_|_|\__, |_| |_|_|_|\__, |_| |_|\__|_|_| |_|\__, |           ~
                   |___/           |___/                   |___/            ~
       
==============================================================================
Section 1: Description                               *simple_highlighting*

Script is designed to be easy and quick to use and satisfy the following
functionality:
1. Highlight multiple different words in multiple different highlight styles.
2. Keep the highlights between buffers.
3. Change search pattern to a highlighted style

==============================================================================
Section 2: Brief example of usage:
  * Place your cursor on a word and use "\h" to highlight it with default slot.
  * Type "\h" over another word to add it to the default slot
  * Run "\h" on a word already in the default highlight slot to remove it
  * ":Hd 3" will change the default slot to slot 3
  * 5\h will highlight the word under the cursor in 5's highlight slot.
  * Change buffer or open new window and highlights will remain the same
  * ":Hc 2"  will clear all the of slots 2's highlights.
  * ":Hs"     to changes the search pattern to all the current highlighted word
  * ":Hc"     will clear all highlights.
  * ":Ha 1 \<aa" will add the regular expression "\<aa" to highlight slot 1
  * ":Hw highlights.so" will save all the curent highlight settings

==============================================================================
Section 3: Detailed description of use:


KEYBINDING

<leader> default is \

[<number>] <Leader> h   -> to highlight the whole word under the cursor,
highlighted colour is determined by the preceding number, if no number
is given 0 is used

numbers can be between 0 to 7 default is 0. More highlight numbers/slots
can be added and there representative colour's changed at the start of
the script.

If the a word (or pattern) is added to a slot that already cointains it
the pattern will be removed.


CHANGING / REMOVING SLOTS

If the word/pattern you are trying to highlight already exits in a slot
it will be removed from the previous slot. If the previous slot is the
same as the one new one (you are trying to add it to the same slot twice)
it will simply remove the word/pattern.


COMMANDS

*Hc* *HighlightClear*
	:Hc [0 2 ...]
Clears the highlighted patterns in slot numbers listed or all if no
number(s) are passed. If you just which to remove one word from the slot
please see changing / removing slots above

*Hs* *HighlightSearch*
	:Hs [0 2 ...]
Changes the search pattern to the highlighted slot numbers listed or
all if no number(s) passed

*Ha* *HighlightAddMultiple*
	:Ha <slot_number> <pattern> [additional patterns ...]
Adds the pattern and any additional patterns (space separated) to the
highlight slot specified in <slot_number>. The patterns support regular
expressions. To include a space use \ as escape character (eg "\ ")

*Hw* *HighlightWrite*
	:Hw <file_location> [0 2 ...]
Create a vim source file at <file_location> containing the settings for
the slot number(s) passed (or all slots if no numbers are passed)
 
To load the file created from HighlightWrite simple source it using
	:source <file_location>


==============================================================================
Section 4: Wrap up

ISSUES:

Currently there are no known bugs.


ALTERNATIVES:
<http://vim.wikia.com/wiki/Highlight_multiple_words> is a very good
alternative to this script. This script is designed to be simple and
easy to use

<http://www.vim.org/scripts/script.php?script_id=2666 > is a much more
compressive and complex script then this one.
 ```
