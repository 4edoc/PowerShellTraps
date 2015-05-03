
Too simple function names in a script is a time bomb. A script may work fine
until it is called in a session with a predefined alias with the same name.
This alias gets invoked by a script, not an internal function, because on
command name resolution PowerShell searches aliases first.

Results are totally unpredictable, of course. A script may even work without
errors doing something unexpected until the problem is revealed somehow.

It looks like a good idea to use the Verb-Noun convention even for internal
function names. This minimizes chances of conflicts. Aliases are not normally
called Verb-Noun.

Scripts

- *MyScript.ps1* defines and invokes the internal function *MyCommand*.
- *Test-MyScript.ps1* shows the potential issue with *MyCommand*.
- *.test.ps1* tests the above.