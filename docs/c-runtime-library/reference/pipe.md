---
title: "_pipe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_pipe"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "pipe"
  - "_pipe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pipe - функция"
  - "pipe - функция"
  - "каналы"
  - "каналы, создание"
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _pipe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Создает канал для чтения и записи.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
  
      int _pipe(  
int *pfds,  
unsigned int psize,  
int textmode   
);  
```  
  
#### Параметры  
 `pfds`\[2\]  
 Массив, который будет содержать файловые идентификаторы для чтения и записи.  
  
 `psize`  
 Объем памяти, который необходимо зарезервировать.  
  
 `textmode`  
 Файловый режим.  
  
## Возвращаемое значение  
 Возвращает 0 в случае успеха.  Возвращает –1 для указания ошибки.  При возникновении ошибки `errno` присваивается одно из следующих значений:  
  
-   `EMFILE`, которая показывает, что больше нет доступных идентификаторов файла.  
  
-   `ENFILE`, которая отображает переполнение системной таблицы файлов.  
  
-   `EINVAL`, которая означает, что либо массив `pfds` является нулевым указателем, либо было передано недопустимое значение для `textmode`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_pipe` создает искусственный *канал* ввода\-вывода, который программа использует для передачи сведений другим программам.  Канал напоминает файл, поскольку он имеет файловый указатель или идентификатор файла \(или и то, и другое\), в него можно писать и из него можно читать путем использования стандартных функций для ввода и вывода библиотеки.  Однако канал не представляет конкретный файл или устройство.  Вместо этого он представляет временное хранилище в памяти, которое не зависит от собственной памяти программы и полностью контролируется операционной системой.  
  
 `_pipe` напоминает `_open`, но открывает каналы для чтения и записи и возвращает два идентификатора файла, а не один.  Программа может использовать обе стороны канала или закрыть ту, которая не используется.  Например, обработчик команд в Windows создает канал во время выполнения команды, такой как `PROGRAM1 | PROGRAM2`.  
  
 Идентификатор стандартного вывода `PROGRAM1` присоединен к идентификатору записи канала.  Стандартный идентификатор ввода `PROGRAM2` присоединен к идентификаторы чтения канала.  Это исключает необходимость создания временных файлов для передачи информации другим программам.  
  
 Функция `_pipe` возвращает два идентификатора файла каналу в аргументе `pfds`.  Элемент `pfds`\[0\] содержит идентификатор чтения, а элемент `pfds`\[1\] содержит идентификатор записи.  Файловые идентификаторы канала используются точно так же, как и другие файловые идентификаторы. \(Низкоуровневые функции ввода и вывода `_read` и `_write` могут считывать из канала и записывать в канал.\) Чтобы определить завершение канала, проверьте запрос `_read`: он должен вернуть 0 прочитанных байтов.  
  
 Аргумент `psize` определяет объем памяти в байтах, который необходимо зарезервировать для канала.  Аргумент `textmode` определяет режим преобразования для канала.  Константа манифеста `_O_TEXT` определяет текстовое преобразование, а константа `_O_BINARY` определяет бинарное преобразование. \(См. [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md) для описания текстового и бинарного режимов.\) Если аргумент `textmode` 0, `_pipe` использует режим преобразования по умолчанию, определенный переменной режима по умолчанию [\_fmode](../../c-runtime-library/fmode.md).  
  
 В многопоточных программах блокировки не выполняются.  Возвращенные идентификаторы файлов вновь открыты, на них не должны ссылаться потоки, пока вызов `_pipe` не завершится.  
  
 Чтобы использовать функцию `_pipe` для обмена данными между родительским и дочерним процессом, каждый процесс должен иметь только один открытый идентификатор в канале.  Идентификаторы должны быть противоположными: если родительский имеет доступ на чтение, то дочерний элемент должен иметь открытым идентификатор записи.  Простейший способ сделать это — использование `OR` \(  `|`\) флаг `_O_NOINHERIT` с `textmode`.  Затем с помощью `_dup` или `_dup2` создать наследуемую копию идентификатора канала, которую вы хотите передать дочернему процессу.  Закройте исходный идентификатор, затем создайте дочерний процесс.  При возвращении значения из вызова функции создания закройте дублированный идентификатор в родительском процессе.  Дополнительные сведения смотрите в примере 2 ниже в данном разделе.  
  
 В операционной системе Windows канал уничтожается, когда все его идентификаторы закрыты. \(Если все идентификаторы чтения канала были закрыты, то запись в канал вызывает ошибку.\) Все операции чтения и записи в канале ожидают, пока не поступит достаточно данных или не будет доступно достаточно свободного пространства в буфере, чтобы завершить запрос ввода\-вывода.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|------------------|----------------------------|------------------------------|  
|`_pipe`|\<io.h\>|\<fcntl.h\>,1 \<errno.h\>2|  
  
 1 Для определений `_O_BINARY` и `_O_TEXT`.  
  
 2 Определения `errno`.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример 1  
  
```  
// crt_pipe.c  
/* This program uses the _pipe function to pass streams of  
 * text to spawned processes.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <io.h>  
#include <fcntl.h>  
#include <process.h>  
#include <math.h>  
  
enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */  
#define NUMPROBLEM 8  
  
int main( int argc, char *argv[] )  
{  
  
   int fdpipe[2];  
   char hstr[20];  
   int pid, problem, c;  
   int termstat;  
  
   /* If no arguments, this is the spawning process */  
   if( argc == 1 )  
   {  
  
      setvbuf( stdout, NULL, _IONBF, 0 );  
  
      /* Open a set of pipes */  
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )  
          exit( 1 );  
  
      /* Convert pipe read descriptor to string and pass as argument   
       * to spawned program. Program spawns itself (argv[0]).  
       */  
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );  
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],   
            hstr, NULL ) ) == -1 )  
          printf( "Spawn failed" );  
  
      /* Put problem in write pipe. Since spawned program is   
       * running simultaneously, first solutions may be done   
       * before last problem is given.  
       */  
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)  
      {  
  
         printf( "Son, what is the square root of %d?\n", problem );  
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );  
  
      }  
  
      /* Wait until spawned program is done processing. */  
      _cwait( &termstat, pid, WAIT_CHILD );  
      if( termstat & 0x0 )  
         printf( "Child failed\n" );  
  
      _close( fdpipe[READ] );  
      _close( fdpipe[WRITE] );  
  
   }  
  
   /* If there is an argument, this must be the spawned process. */  
   else  
   {  
  
      /* Convert passed string descriptor to integer descriptor. */  
      fdpipe[READ] = atoi( argv[1] );  
  
      /* Read problem from pipe and calculate solution. */  
      for( c = 0; c < NUMPROBLEM; c++ )  
      {  
  
        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );  
        printf( "Dad, the square root of %d is %3.2f.\n",  
                 problem, sqrt( ( double )problem ) );  
  
      }  
   }  
}  
```  
  
## Пример результатов выполнения  
  
```  
Son, what is the square root of 1000?  
Son, what is the square root of 2000?  
Son, what iDad, the square root of 1000 is 31.62.  
Dad, the square root of 2000 is 44.72.  
s the square root of 3000?  
Dad, the square root of 3000 is 54.77.  
Son, what is the square root of 4000?  
Dad, the square root of 4000 is 63.25.  
Son, what is the square root of 5000?  
Dad, the square root of 5000 is 70.71.  
Son, what is the square root of 6000?  
SonDad, the square root of 6000 is 77.46.  
, what is the square root of 7000?  
Dad, the square root of 7000 is 83.67.  
Son, what is the square root of 8000?  
Dad, the square root of 8000 is 89.44.  
```  
  
## Пример 2  
 Это простое фильтрующее приложение.  Оно создает приложение crt\_pipe\_beeper после того, как оно создает канал, который направляет stdout созданного приложения на фильтр.  Фильтр удаляет символ ASCII 7 \(звуковой сигнал\).  
  
```  
// crt_pipe_beeper.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   int   i;  
   for(i=0;i<10;++i)  
      {  
         printf("This is speaker beep number %d...\n\7", i+1);  
      }  
   return 0;  
}  
```  
  
 Само фильтрующее приложение:  
  
```  
// crt_pipe_BeepFilter.C  
// arguments: crt_pipe_beeper.exe  
  
#include <windows.h>  
#include <process.h>  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
#define   OUT_BUFF_SIZE 512  
#define   READ_FD 0  
#define   WRITE_FD 1  
#define   BEEP_CHAR 7  
  
char szBuffer[OUT_BUFF_SIZE];  
  
int Filter(char* szBuff, ULONG nSize, int nChar)  
{  
   char* szPos = szBuff + nSize -1;  
   char* szEnd = szPos;  
   int nRet = nSize;  
  
   while (szPos > szBuff)  
   {  
      if (*szPos == nChar)  
         {  
            memmove(szPos, szPos+1, szEnd - szPos);  
            --nRet;  
         }  
      --szPos;  
   }  
   return nRet;  
}  
  
int main(int argc, char** argv)  
{  
   int nExitCode = STILL_ACTIVE;  
   if (argc >= 2)  
   {  
      HANDLE hProcess;  
      int fdStdOut;  
      int fdStdOutPipe[2];  
  
      // Create the pipe  
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)  
         return   1;  
  
      // Duplicate stdout file descriptor (next line will close original)  
      fdStdOut = _dup(_fileno(stdout));  
  
      // Duplicate write end of pipe to stdout file descriptor  
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)  
         return   2;  
  
      // Close original write end of pipe  
      _close(fdStdOutPipe[WRITE_FD]);  
  
      // Spawn process  
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],   
       (const char* const*)&argv[1]);  
  
      // Duplicate copy of original stdout back into stdout  
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)  
         return   3;  
  
      // Close duplicate copy of original stdout  
      _close(fdStdOut);  
  
      if(hProcess)  
      {  
         int nOutRead;  
         while   (nExitCode == STILL_ACTIVE)  
         {  
            nOutRead = _read(fdStdOutPipe[READ_FD],   
             szBuffer, OUT_BUFF_SIZE);  
            if(nOutRead)  
            {  
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);  
               fwrite(szBuffer, 1, nOutRead, stdout);  
            }  
  
            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))  
               return 4;  
         }  
      }  
   }  
   return nExitCode;  
}  
```  
  
## Output  
  
```  
This is speaker beep number 1...  
This is speaker beep number 2...  
This is speaker beep number 3...  
This is speaker beep number 4...  
This is speaker beep number 5...  
This is speaker beep number 6...  
This is speaker beep number 7...  
This is speaker beep number 8...  
This is speaker beep number 9...  
This is speaker beep number 10...  
```  
  
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Для получения дополнительной информации см. [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)