# Notepad-s
;Variables Global $g_bPaused = False Local $hWnd  HotKeySet("{PAUSE}", "TogglePause") HotKeySet("{END}", "Terminate")  Start()  Func Start()    ; Press Esc to terminate script, Pause/Break to "pause"    ; Retrieve the handle of the Notepad window using the classname of Notepad.    $hWnd = WinGetHandle("[CLASS:Notepad]")    If @error Then       OpenNotepad()       Start()    Else       ;Start writing 1 to 100 in Notepad       StartCount()    EndIf     ; Close the Notepad window using the handle returned by WinGetHandle.    Sleep ( 5000 )    WinClose($hWnd) EndFunc   ;==>Start  Func OpenNotepad()    ; Run Notepad    Run("notepad.exe")     ; Wait 10 seconds for the Notepad window to appear.    WinWait("[CLASS:Notepad]", "", 10) EndFunc ;==>OpenNotepad
