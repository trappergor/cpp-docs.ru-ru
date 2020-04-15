---
title: _pipe
ms.date: 4/2/2020
api_name:
- _pipe
- _o__pipe
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- pipe
- _pipe
helpviewer_keywords:
- pipes, creating
- _pipe function
- pipes
- pipe function
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
ms.openlocfilehash: 5bac435bed26decee0069f5814d1f3d25a54470a
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81338499"
---
# <a name="_pipe"></a>_pipe

Создает канал для чтения и записи.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _pipe(
   int *pfds,
   unsigned int psize,
   int textmode
);
```

### <a name="parameters"></a>Параметры

*pfds*<br/>
Указатель на массив из двух **int** для удержания чтения и записи дескрипторов файлов.

*psize*<br/>
Объем памяти, который необходимо зарезервировать.

*textmode*<br/>
Файловый режим.

## <a name="return-value"></a>Возвращаемое значение

Возвращает 0 в случае успеха. Возвращает -1 для указания ошибки. При ошибке **errno** устанавливается на одно из следующих значений:

- **EMFILE**, что указывает на то, что больше не доступны дескрипторы файлов.

- **ENFILE**, который указывает на переполнение системного файла-таблицы.

- **EINVAL**, который указывает, что либо массив *pfds* является нулевой указатель или что недействительное значение для *textmode* был передан дюйма

Для получения дополнительной информации об этих и других кодах возврата [_sys_nerr _sys_errlist _doserrno](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md)см.

## <a name="remarks"></a>Remarks

Функция **_pipe** создает *трубу,* которая представляет собой искусственный канал ввоза/о, который программа использует для передачи информации другим программам. Канал похож на файл, поскольку он имеет файловый указатель или дескриптор файла (или и то, и другое), и в него можно записывать и из него можно считывать данные с помощью стандартных библиотечных функций ввода и вывода. Однако канал не представляет конкретный файл или устройство. Вместо этого он представляет временное хранилище в памяти, которое не зависит от собственной памяти программы и полностью контролируется операционной системой.

**_pipe** напоминает **_open** но открывает трубку для чтения и письма и возвращает два файла дескрипторов вместо одного. Программа может использовать обе стороны канала или закрыть ту сторону, которая не используется. Например, командный процессор в Windows создает трубу при выполнении такой команды, как **PROGRAM1** | **PROGRAM2.**

Стандартный дескриптор **выхода PROGRAM1** крепится к дескриптору записи трубы. Стандартный дескриптор ввода **PROGRAM2** крепится к прочитанному дескриптору трубы. Это исключает необходимость создания временных файлов для передачи информации другим программам.

**Функция _pipe** возвращает два дескриптора файлов в трубу в аргументе *pfds.* Элемент *pfds*содержит дескриптор чтения, а элемент *pfds*содержит дескриптор. Дескрипторы файлов канала используются точно так же, как и другие дескрипторы файлов. (Низкоуровневые вхотворные и выходные функции **_read** и **_write** могут читать и писать в трубу.) Чтобы обнаружить состояние конца трубы, проверьте **запрос _read,** который возвращает 0 по мере чтения количества байтов.

Аргумент *psize* определяет количество памяти, в байтах, для резервирования для трубы. Аргумент *textmode* определяет режим перевода для трубы. Явный постоянный **_O_TEXT** определяет текстовый перевод, а постоянная **_O_BINARY** определяет бинарный перевод. [(См. fopen, _wfopen](fopen-wfopen.md) для описания текста и двоичных режимов.) Если аргумент *textmode* радостоит 0, **_pipe** использует режим перевода по умолчанию, указанный переменным _fmode режима по умолчанию [_fmode](../../c-runtime-library/fmode.md).

В многопоточных программах блокировки не выполняются. Возвращаются дескрипторы файлов, которые недавно открыты и не должны ссылаться ни на один поток до завершения **_pipe** вызова.

Чтобы использовать **функцию _pipe** для связи между родительским процессом и процессом ребенка, каждый процесс должен иметь только один дескриптор, открытый на трубе. Дескрипторы должны быть противоположными: если родительский процесс имеет доступ на чтение, то дочерний процесс должен иметь открытый дескриптор записи. Самый простой способ сделать это, чтобы bitwise или ( )**|** **_O_NOINHERIT** флаг с *textmode*. Затем используйте **_dup** или **_dup2** для создания наследуемой копии трубопрокатного дескриптора, который вы хотите передать ребенку. Закройте исходный дескриптор, затем создайте дочерний процесс. После возвращения из вызова spawn закройте дублирующий дескриптор в родительском процессе. Дополнительные сведения смотрите в примере 2 ниже в данном разделе.

В операционной системе Windows при закрытии всех дескрипторов канала он уничтожается. (Если все прочитавшие дескрипторы на трубе были закрыты, то написание в трубу вызывает ошибку.) Все операции чтения и записи на трубе ждут, пока не будет достаточно данных или достаточно буферного пространства для выполнения запроса ввоза/о.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_pipe**|\<io.h>|\<fcntl.h>,1 \<errno.h>2|

1 Для **определений _O_BINARY** и **_O_TEXT.**

2 **ошибочных** определения.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

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

## <a name="see-also"></a>См. также раздел

[Управление процессами и средой](../../c-runtime-library/process-and-environment-control.md)<br/>
[_open, _wopen](open-wopen.md)<br/>
