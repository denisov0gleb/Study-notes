# AutoHotKey API #

Based on [russian wiki](https://ahk-wiki.ru/)

Created 16.09.20 by **DGL**

Modified 17.09.20 by **DGL**

# Table of Content:

<!-- vim-markdown-toc GFM -->

1. [Make your script autorun when PC in on](#make-your-script-autorun-when-pc-in-on)
1. [Language syntax](#language-syntax)
	1. [Variables](#variables)
		1. [Strings operations](#strings-operations)
		1. [Special variables](#special-variables)
	1. [Conditions](#conditions)
	1. [Loops](#loops)
		1. [For](#for)
		1. [While](#while)
		1. [Break and Continue](#break-and-continue)
	1. [Functions](#functions)
	1. [Commands](#commands)
	1. [Run program or link](#run-program-or-link)
1. [Files](#files)
1. [GUI commands](#gui-commands)
	1. [Special windows](#special-windows)
		1. [Message Box](#message-box)
		1. [Input Box](#input-box)
		1. [Files windows](#files-windows)
	1. [Icons](#icons)
	1. [Windows](#windows)
	1. [Mouse](#mouse)
	1. [Colors](#colors)
1. [Keys](#keys)
	1. [Keys code](#keys-code)
	1. [Keybinding](#keybinding)
	1. [Key emulation](#key-emulation)
1. [Autocorrect](#autocorrect)
1. [Code examples](#code-examples)

<!-- vim-markdown-toc -->

## Make your script autorun when PC in on ##

1. Copy your script (`Ctrl + c`)
2. Open Run dialog (`Win + r`) and enter `shell:startup`
3. Right mouse click and select *Paste ShortCut*


## Language syntax ##
[Table of Content](#table-of-content)

`; comment`


`Shutdown, 1`

`Return`

`Sleep, time_in_milliseconds`

`Send, something`

`Loop, number`

`==` - equal



### Variables ###

Max variable length  is 254 symbols (cyrillic included), can contain **any** letter, number or symbol **\# \_ \@ \$ \& \[ \]**.

Save value to variable:

`bool_val := true`

Get variable value:

`%bool_val%`

| Type			| Values																 | Example							 |
| ---				| ---																		 | ---									 |
| Boolean		| **0** or **1** (**false** or **true**) | bool_val := true			 |
| Numerical | any **integer** or **decimal**				 | numerical_val := 0		 |
| Strings		| any **strings**												 | string := "your name" |

#### Strings operations ####
* contancation: `MyStr = %str1% %str2%`

#### Special variables ####

* Clipboard

```AutoHotKey
F7::MsgBox %clipboard%
```

* Program Files `%A_ProgramFiles%`

* iterator `A_Index`



### Conditions ###

**if** conditions:

```AutoHotKey
check := false

^1::
if(check)
	MsgBox, Check = %check% ; true
else
	MsgBox, Check = %check% ; false
check := !check
Return
```


**if-else** conditions:

```AutoHotKey
if(A_Hour < 6)
	state = night
else if(A_Hour < 10)
	state = morning
else if(A_Hour < 17)
	state = day
else
	state = evening
	
MsgBox, Now is %state%, %A_Hour% o'clock
```

### Loops ###

#### For ####

**Loop** - *for* analog:

```AutoHotKey
^1::
	Loop, 5
		MsgBox, This is the %A_Index% iteration
```

**Loop** can run infinite till the **Break** or **Return** word.

Variable **A_Index** contains the current iteration.
Outside the **Loop** **A_Index** always is **0**.

#### While ####

**while** loop:

```AutoHotKey
~LButton::
	while(GetKeyState("LButton"))
	{
		ToolTip, Leave left mouse key alone!
		Sleep, 100
	}
	ToolTip
return
```

or

```AutoHotKey
; The Tooltip show the sizes of mouse highlight rectangle

CoordMode, Mouse, Screen

~LButton::
	MouseGetPos, begin_x, begin_y
	While GetKeyState("LButton")
	{
		MouseGetPos, x, y
		ToolTip, % begin_x ", " begin_y "`n" Abs(begin_x-x) " x " Abs(begin_y-y)
		Sleep, 10
	}
	ToolTip
return
```

#### Break and Continue ####

**Break** and **Continue** can be used only inside the loops.



### Functions ###

```AutoHotKey
; Function example:
; Function(par1, par2, par3)

MyVar := SubStr("I'm scripting, awesome!", 16)
SunStr(37*12, 1, 2)
```

### Commands ###
```language
; Command example:
; Command, par1, par2, par3
```


### Run program or link ###

Running another program:

```AutoHotKey
Run, %A_ProgramFiles%\Some_Program\Program.exe
```

Open link in web-browser:

```AutoHotKey
Run, https://ahk-wiki.ru
```

Possible ways to **run** the program:

```AutoHotKey
#z::
	Run, Notepad, , max
	Run, Notepad, , min
	Run, Notepad, , hide
Return
```

Use additional arguments for **run**ning the program:

```AutoHotKey
; Use C:\My Documents as the parent folder
; %comspec% usually is equal to C:\Windows\System32\cmd.exe
#c::Run, %comspec% /k, C:\My Documents
```

There are several **system verbs**:

```AutoHotKey
; Open properties manager
Run, properties "C:\Address List.txt"

; Send file to the printer
Run, print "C:\Address List.txt"
```

`RunWait` - run a program after closing another program

```AutoHotKey
F7::
RunWait, Notepad
MsgBox, Notepad is closed{!}
Return
```

## Files ##

Append to existing file or create a new one:

`FileAppend, This text will be appended.\n, C:\My Documents\My Text File.txt`

Delete file:

`FileDelete, C:\My Documents\My Text File.txt`

Main file commands:

* `FileRead`
* `IfExist`
* `File-reading Loop`
* `FileSelectFile`
* `FileSelectFolder`
* `FileCopy`
* `FileMove`
* `File Loop` search files or folders
* `FileSetAttrib` change file attributes
* `FileSetTime` change creation date
* *.INI* files:
	* `IniRead`
	* `IniWrite`
	* `IniDelete`
* windows register files:
	* `RegRead`
	* `RegWrite`
	* `RegDelete`
	* `Register Loop`






## GUI commands ##

### Special windows ###

#### Message Box ####

```AutoHotKey
MsgBox, Some text on the Message Box
```

`IfMsgBox, No, Return`

#### Input Box ####

```AutoHotKey
InputBox,
```

#### Files windows ####
* `FileSelectFile`
* `FileSelectFolder`



### Icons ###

To add special icon to the tray:
`Menu, Tray, Icon, D:\IconsCollection\Skulls\0050.ico, 1`


### Windows ###

Windows can be activated with **WinActivate** command:

```AutoHotKey
IfWinExist, Untitled - Notepad
{
	WinActivate
}
else
{
	Run, Notepad
	WinWait, Untitled - Notepad
	WinActivate
}
```

Main windows commands:

* `IfWinActive`
* `WinWaitActive`
* `WinClose`
* `WinMove`
* `WinMinimize`
* `WinMaximize`
* `WinRestore`

### Mouse ###

Use *Window Spy* to get the Mouse position on current window (starts count from the left upper
corner).

Click the left mouse button on the current window position
```AutoHotKey
F7::MouseClick, Left, 112, 223
```
Main mouse commands:
* `MouseMove`
* `MouseClickDrag`


### Colors ###

Get color in the position (11;22)
`PixelGetColor, Color, 11, 22`


## Keys ##

### Keys code ###

[Keys codes] (https://www.autohotkey.com/docs/KeyList.htm)

\# - *windows*
\^ - *ctrl*

### Keybinding ###


Single line keybinding:

```AutoHotKey
^1::MsgBox, pushed **Ctrl+1**
```

Multiple line keybinding:

```AutoHotKey
^2::
MsgBox, You pushed **Ctrl+2**
Sleep, 3000
MsgBox, Wait 3 sec and new window appear.
Return
```

### Key emulation ###

```AutoHotKey
; Send text line after pushing **1** key:
1::Send, Hello, could I help you somehow?{Enter}New line text.

; Simply '!' is equal to **Alt** key => use {!}:
2::Send, Thank you and goodbye{!}

; Call **Ctlr+Shift+Esc** => task manager:
3::Send, ^+{Esc}

; Push down **Alt** key and switch 5 times the current program window
4::
Send, {Alt down}
Loop, 5
{
	Send, {Tab}
	Sleep, 500
}
Send, {Alt up}
Return
```


## Autocorrect ##

Single line autocorrect:

```AutoHotKey
::wft::What the fuck
```

Multiple line autocorrect:

```AutoHotKey
::bb::
MsgBox, Shutdown the PC... Now!
Shutdown, 1
Return
```


## Code examples ##

For testing and troubleshooting add to script to exit with **Esc** button:

```AutoHotKey
Esc::ExitApp	; Exit script with Escape key
```

Different action for many key pushing (timer) *(on russian)*:

```AutoHotKey
; Пример №3: Определяет, сколько раз подряд была нажата горячая клавиша.
; В зависимости от количества выполненных нажатий варьируется и резуль-
; тат - выполняется первое, второе или третье задание соответственно:

#c::
;----------------------------------------------------- Block #2 --//
; Команда SetTimer уже запущена, но прежде, чем она сработает,
	; мы успеем собрать данные о количестве нажатий наших горячих клавиш:

	If WinC_Presses > 0
{
	WinC_Presses += 1
		Return
}
;----------------------------------------------------- Block #1 --//
; А вот и наше первое нажатие горячих клавиш. Устанавливаем число нажатий
; равное 1 и запускаем таймер:

WinC_Presses = 1
SetTimer, KeyWinC, 1000 ; Идет ожидание количества нажатий клавиш
; в течение 1000 миллисекунд.
Return

;----------------------------------------------------- Block #3 --//
KeyWinC:
SetTimer, KeyWinC, Off ; отключение таймера.
If WinC_Presses = 1 ; Если было всего одно нажатие горячих клавиш.
{
	Run, C:\	; Открывается папка C:\.
}
Else If WinC_Presses = 2 ; Если горячие клавиши нажимались дважды.
{
	Run, D:\	; Открывается другая папка - D:\.
}
Else If WinC_Presses > 2
{
	SplashTextOn, 400, 180, Зачем???,
		(
		 `n Вы нажали `n горячие клавиши `n три или более раз.
		 `n`n А это запрещено! :)
			)
			Sleep, 3000
			SplashTextOff
}
;----------------------------------------------------- Block #4 --//
; Вне зависимости от того, какое действие было выполнено, сбрасываем
; значение нашей переменной на ноль, чтобы подготовиться к следующей
; серии нажатий:

WinC_Presses = 0
Return
```

Autoclose openning windows (timer) *(on russian)*:

```AutoHotKey
; Пример №1: Закрытие нежелательных окон при их появлении:
#Persistent
SetTimer, CloseMailWarnings, 250
return

CloseMailWarnings:
	WinClose, Microsoft Outlook, A timeout occured while communicating
	WinClose, Microsoft Outlook, A connection to the server could not be established
return
```



