<div align="center">

## Ghost Typer


</div>

### Description

The perfect April Fool's Day Prank! It simulates a user typing random scary messages every 45 seconds. Imagine typing up a report in a word processor when all of a sudden the words "I'm watching you...", appears on the screen all of a sudden.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Brenton Andrew Saunders](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/brenton-andrew-saunders.md)
**Level**          |Intermediate
**User Rating**    |4.6 (32 globes from 7 users)
**Compatibility**  |Microsoft Visual C\+\+
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/brenton-andrew-saunders-ghost-typer__3-10405/archive/master.zip)





### Source Code

```
#include <windows.h>
#include <stdlib.h>
#define NUM_MESSAGES 11
CHAR szMessage[NUM_MESSAGES][255] = {"i'm watching you...", // Just some scary messages
									 "did you lock the door",
									 "are you alone",
									 "they're coming...",
									 "leave while you can...",
									 "it's here...",
									 "i know where you are...",
									 "did you check the kids",
									 "don't turn around...",
									 "help me...",
									 "it's only a matter of time..."};
int WINAPI WinMain(HINSTANCE hInstance, HINSTANCE hPrevInstance, LPSTR lpCmdLine, int nShowCmd)
{
	srand(GetTickCount());
	while(TRUE) // Main loop; Keeps the program running
	{
		Sleep(45000); // Pause for a few seconds to scare whoever is onleave while you the computer
		INT nRand = (rand() % NUM_MESSAGES); // Pick a random message to display
		for(INT i = 0; i < lstrlen(szMessage[nRand]); i ++)
		{
			// Simulate a person typing
			keybd_event((UCHAR)VkKeyScan(szMessage[nRand][i]), NULL, NULL, NULL);
			Sleep(rand() % 200);
		}
	}
	return 0;
}
```

