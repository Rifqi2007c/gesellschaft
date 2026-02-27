### diable start web search result
- open regedit go to `Computer\HKEY_LOCAL_MACHINE\SOFTWARE\Policies\Microsoft\Windows\Explorer`
- create DWORD (32-bit) value name `DisableSearchBoxSuggestions`
- set `DisableSearchBoxSuggestions` value data to 1

### change multiselect color
- open regedit, go to:
`HKEY_CURRENT_USER\Contorl Panel\Colors`
- change `HotTrackingColor` and `Hilight` rgb value
----
#windows 