# _WD_IsWindowTop
*** Now you can jump into Frame 2 ;~ ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2 = '" &amp; _WD_FrameEnter($sSession, 1) &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2 = '" &amp; _WD_FrameEnter($sSession, "nest2") &amp; "'" &amp; @CRLF) $sElement = _WD_FindElement($sSession, $_WD_LOCATOR_ByXPath, "//h3") ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Nest2 text = '" &amp; _WD_ElementAction($sSession, $sElement, 'text') &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "   Am I at the Top level? = '" &amp; _WD_IsWindowTop($sSession) &amp; "'" &amp; @CRLF &amp; @CRLF)  ;*** Now you can jump into a nested frame inside Frame 2 ;~ ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2.3 = '" &amp; _WD_FrameEnter($sSession, 2) &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2.3 = '" &amp; _WD_FrameEnter($sSession, "nest2.3") &amp; "'" &amp; @CRLF) $sElement = _WD_FindElement($sSession, $_WD_LOCATOR_ByXPath, "//h3") ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Nest2.3 text = '" &amp; _WD_ElementAction($sSession, $sElement, 'text') &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "   Am I at the Top level? = '" &amp; _WD_IsWindowTop($sSession) &amp; "'" &amp; @CRLF &amp; @CRLF)  ;*** Now you can jump into a nested-nested frame inside Frame 2 (I.e. nested inside Frame 2.3) ;~ ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2.3.4 = '" &amp; _WD_FrameEnter($sSession, 3) &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go into frame 2.3.4 = '" &amp; _WD_FrameEnter($sSession, "nest2.3.4") &amp; "'" &amp; @CRLF) $sElement = _WD_FindElement($sSession, $_WD_LOCATOR_ByXPath, "//h3") ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Nest2.3.4 text = '" &amp; _WD_ElementAction($sSession, $sElement, 'text') &amp; "'" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "   Am I at the Top level? = '" &amp; _WD_IsWindowTop($sSession) &amp; "'" &amp; @CRLF &amp; @CRLF)  ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "*** Loop to drill to the Top ***" &amp; @CRLF) ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Am I at the Top level? = '" &amp; _WD_IsWindowTop($sSession) &amp; "'" &amp; @CRLF) While _WD_IsWindowTop($sSession) = False     ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "Go up 1 parent frame = '" &amp; _WD_FrameLeave($sSession) &amp; "'" &amp; @CRLF)     $sElement = _WD_FindElement($sSession, $_WD_LOCATOR_ByXPath, "//h3")     ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "H3 text = '" &amp; _WD_ElementAction($sSession, $sElement, 'text') &amp; "'" &amp; @CRLF)     ConsoleWrite(@ScriptLineNumber &amp; @TAB &amp;  "   Am I at the Top level? = '" &amp; _WD_IsWindowTop($sSession) &amp; "'" &amp; @CRLF) WEnd
