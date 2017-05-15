---
title: "_pipe | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _pipe
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- pipe
- _pipe
dev_langs:
- C++
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 20
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: 3f91eafaf3b5d5c1b8f96b010206d699f666e224
ms.openlocfilehash: 23bcf7a96dfbfa7719b20f2a035ddcbc93c835ee
ms.contentlocale: ru-ru
ms.lasthandoff: 04/01/2017

---
# <a name="pipe"></a>_pipe
Создает канал для чтения и записи.  
  
> [!IMPORTANT]
>  Этот API не может использоваться в приложениях, выполняемых в [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)]. Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом /ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _pipe(  
   int *pfds,  
   unsigned int psize,  
   int textmode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pfds`[2]  
 Массив, который будет содержать дескрипторы файлов для чтения и записи.  
  
 `psize`  
 Объем памяти, который необходимо зарезервировать.  
  
 `textmode`  
 Файловый режим.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает 0 в случае успеха. Возвращает значение-1 для указания ошибки. При возникновении ошибки параметру `errno` присваивается одно из следующих значений:  
  
-   `EMFILE`, которое означает, что больше нет доступных дескрипторов файлов.  
  
-   `ENFILE`, которое указывает на переполнение системной таблицы файлов.  
  
-   `EINVAL`, которое означает, что либо массив `pfds` является указателем NULL, либо передано недопустимое значение для `textmode`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_pipe` создает искусственный *канал* ввода-вывода, который программа использует для передачи сведений другим программам. Канал похож на файл, поскольку он имеет файловый указатель или дескриптор файла (или и то, и другое), и в него можно записывать и из него можно считывать данные с помощью стандартных библиотечных функций ввода и вывода. Однако канал не представляет конкретный файл или устройство. Вместо этого он представляет временное хранилище в памяти, которое не зависит от собственной памяти программы и полностью контролируется операционной системой.  
  
 Функция `_pipe` похожа на функцию `_open`, но открывает канал для чтения и записи и возвращает два дескриптора файла, а не один. Программа может использовать обе стороны канала или закрыть ту сторону, которая не используется. Например, обработчик команд в Windows создает канал во время выполнения команды, такой как `PROGRAM1 | PROGRAM2`.  
  
 Дескриптор стандартного вывода `PROGRAM1` присоединен к дескриптору записи канала. Стандартный дескриптор ввода `PROGRAM2` присоединен к дескриптору чтения канала. Это исключает необходимость создания временных файлов для передачи информации другим программам.  
  
 Функция `_pipe` возвращает два дескриптора файлов для канала в аргументе `pfds`. Элемент `pfds`[0] содержит дескриптор чтения, а элемент `pfds`[1] содержит дескриптор записи. Дескрипторы файлов канала используются точно так же, как и другие дескрипторы файлов. (Низкоуровневые функции ввода и вывода `_read` и `_write` могут считывать из канала и записывать в канал.) Чтобы обнаружить состояние завершения канала, проверьте запрос `_read`, который возвращает 0 прочитанных байтов.  
  
 Аргумент `psize` указывает объем памяти в байтах, который необходимо зарезервировать для канала. Аргумент `textmode` определяет режим преобразования для канала. Константа манифеста `_O_TEXT` задает текстовое преобразование, а константа `_O_BINARY` задает двоичное преобразование. (Описание текстового и двоичного режимов см. в разделе [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md).) Если аргумент `textmode` равен 0, функция `_pipe` использует режим преобразования по умолчанию, определенный переменной режима по умолчанию [_fmode](../../c-runtime-library/fmode.md).  
  
 В многопоточных программах блокировки не выполняются. Возвращенные дескрипторы файлов только что открыты, на них не должны ссылаться никакие потоки, пока вызов `_pipe` не завершится.  
  
 Чтобы использовать функцию `_pipe` для обмена данными между родительским и дочерним процессами, каждый процесс должен иметь только один открытый дескриптор в канале. Дескрипторы должны быть противоположными: если родительский процесс имеет доступ на чтение, то дочерний процесс должен иметь открытый дескриптор записи. Простейший способ сделать это — использовать `OR` (`|`) флаг `_O_NOINHERIT` с `textmode`. Затем с помощью функции `_dup` или `_dup2` создать наследуемую копию дескриптора канала, который требуется передать дочернему процессу. Закройте исходный дескриптор, затем создайте дочерний процесс. После возвращения из вызова spawn закройте дублирующий дескриптор в родительском процессе. Дополнительные сведения смотрите в примере 2 ниже в данном разделе.  
  
 В операционной системе Windows при закрытии всех дескрипторов канала он уничтожается. (Если закрыты все дескрипторы чтения канала, запись в канал вызывает ошибку.) Все операции чтения и записи в канале ожидают, пока не поступит достаточно данных или не будет доступно достаточно свободного пространства в буфере, чтобы завершить запрос ввода-вывода.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_pipe`|\<io.h>|\<fcntl.h>,1 \<errno.h>2|  
  
 1 Для определений `_O_BINARY` и `_O_TEXT`.  
  
 2 Определения `errno`.  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example-1"></a>Пример 1  
  
```C  
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
  
```Output  
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
  
## <a name="example-2"></a>Пример 2  
 Это простое фильтрующее приложение. Оно создает приложение crt_pipe_beeper после создания канала, который направляет поток stdout созданного приложения на фильтр. Фильтр удаляет символ ASCII 7 (звуковой сигнал).  
  
```C  
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
  
```C  
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
  
```Output  
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
  
## <a name="see-also"></a>См. также  
 [Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)
