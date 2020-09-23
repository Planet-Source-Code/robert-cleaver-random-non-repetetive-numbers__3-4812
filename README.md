<div align="center">

## Random Non Repetetive Numbers


</div>

### Description

This program fills an array[20] with random numbers between 1 and 20, without repeating a number. This code can be used for encryption, games, testing software and much much more. give me some credit if you use it, and if you like it vote.. if you change it, please send me the updated version. thanks for downloading it.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Robert Cleaver](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/robert-cleaver.md)
**Level**          |Advanced
**User Rating**    |4.8 (24 globes from 5 users)
**Compatibility**  |C\+\+ \(general\), Borland C\+\+
**Category**       |[Algorithms](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/algorithms__3-29.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/robert-cleaver-random-non-repetetive-numbers__3-4812/archive/master.zip)





### Source Code

```
/*
 Name: Robert Cleaver
 Date: 9 - 17 - 02
 Prog: RANDOM.CPP
 Desc: Generates a non-repetetive random number
*/
#include<iostream.h>
#include<conio.h>
#include<stdlib.h>
typedef int itype[20];
void DoRandom(itype &RandomArr);
int check(itype &RandomArr, int ArrayIndex);
int main()
{
	clrscr();
	randomize();
	itype RandomArr;
	DoRandom(RandomArr);
	getch();
	return(0);
}
void DoRandom(itype &RandomArr)
{
	int FillLoop;
	FillLoop = 0;
	RandomArr[1] = (rand() % 20) + 1;
	for (FillLoop = 2; FillLoop <= 20; FillLoop++)
	{
		RandomArr[FillLoop] = (rand() % 20) + 1;
		while (check(RandomArr,FillLoop) != 1)
		{
			RandomArr[FillLoop] = (rand() % 20) + 1;
		}
		cout<<FillLoop<<": "<<RandomArr[FillLoop]<<endl;
	}
}
int check(itype &RandomArr, int ArrayIndex)
{
	int CheckLoop, nomatch;
	nomatch = 0;
	CheckLoop = 0;
	for (CheckLoop = 1; CheckLoop < ArrayIndex; CheckLoop++)
	{
		if (RandomArr[CheckLoop] == RandomArr[ArrayIndex])
		{
			nomatch = 1;
			return(0);
		}
		else if (CheckLoop == (ArrayIndex - 1) && nomatch == 0)
		{
			return(1);
		}
	}
}
```

