---
title: "freopen, _wfreopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "freopen"
  - "_wfreopen"
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
  - "_wfreopen"
  - "_tfreopen"
  - "freopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tfreopen - функция"
  - "_wfreopen - функция"
  - "указатели файлов [C++], повторное назначение"
  - "freopen - функция"
  - "tfreopen - функция"
  - "wfreopen - функция"
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# freopen, _wfreopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Переназначает указатель файла.  Существуют более безопасные версии этих функций; см. раздел [freopen\_s, \_wfreopen\_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
## Синтаксис  
  
```  
FILE *freopen(   
   const char *path,  
   const char *mode,  
   FILE *stream   
);  
FILE *_wfreopen(   
   const wchar_t *path,  
   const wchar_t *mode,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `path`  
 Путь к новому файлу.  
  
 `mode`  
 Тип разрешенного доступа.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает указатель на вновь открытый файл.  Если возникает ошибка, исходный файл закрывается, а функция возвращает значение указателя `NULL`.  Если параметр `path`, `mode` или `stream` является нулевым указателем либо `filename` является пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `NULL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Существуют более безопасные версии этих функций; см. раздел [freopen\_s, \_wfreopen\_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
 Функция `freopen` закрывает файл, связанный в данный момент с `stream`, и связывает `stream` с файлом, указанным аргументом `path`*.* `_wfreopen` является версией `_freopen` с расширенными символами; аргументы `path` и `mode` в `_wfreopen` — строки расширенных символов.  Поведение `_wfreopen` и `_freopen` идентично в противном случае.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen` обычно используется для перенаправления заранее открытых файлов `stdin`, `stdout` и `stderr` на файлы, определенные пользователем.  Новый файл, связанный с `stream`, открывается с `mode`*,* — символьной строкой, указывающей запрошенный тип доступа для файла, следующим образом:  
  
 `"r"`  
 Открывает для чтения.  Если файл не существует или его невозможно найти, вызов `freopen` завершается ошибкой.  
  
 `"w"`  
 Открывает пустой файл для записи.  Если указанный файл существует, его содержимое удаляется.  
  
 `"a"`  
 Открывает для записи в конце файла \(добавление\) без удаления маркера конца файла перед записью новых данных в файл; создает файл, если он не существует.  
  
 `"r+"`  
 Открывает для чтения и записи.  \(Файл должен существовать.\)  
  
 `"w+"`  
 Открывает пустой файл для чтения и записи.  Если указанный файл существует, его содержимое удаляется.  
  
 `"a+"`  
 Открывает для чтения и добавления; операция добавления включает в себя удаление маркера конца файла перед записью новых данных в файл и восстановление маркера конца файла после завершения записи; создает файл, если он не существует.  
  
 Используйте типы `"w"` и `"w+"` с осторожностью, поскольку они могут приводить к уничтожению существующих файлов.  
  
 Если файл открывается с помощью типа доступа `"a"` или `"a+"`, все операции записи выполняются в конце файла.  Хотя указатель файла может быть перемещен с помощью `fseek` или `rewind`, он всегда возвращается в конец файла перед выполнением любой операции записи.  Поэтому перезаписать существующие данные невозможно.  
  
 Режим `"a"` не удаляет маркер конца файла перед добавлением в файл.  После добавления команда MS\-DOS TYPE отображает данные только до первоначального маркера EOF и не отображает данные, добавленные в файл.  Перед добавлением в файл режим `"a+"` удаляет маркер конца файла.  После добавления команда TYPE MS\-DOS отображает все данные в файле.  Режим `"a+"` необходим для добавления в потоковый файл, завершаемый маркером конца файла CTRL\+Z.  
  
 Если задан тип доступа `"r+"`, `"w+"` или `"a+"`, чтение и запись разрешены \(считается, что файл открыт для "обновления"\).  Однако при переключении между чтением и записью необходимо выполнить промежуточную операцию [fsetpos](../Topic/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) или [rewind](../../c-runtime-library/reference/rewind.md).  При необходимости для операции `fsetpos` или `fseek` можно задать текущее положение.  Помимо вышеуказанных значений один из следующих символов может быть включен в строку `mode` для определения режима преобразования новых строк.  
  
 `t`  
 Открыть в текстовом режиме \(преобразование\); сочетания символов возврата каретки и перевода строки преобразуются в один символ перевода строки на входе, а символы перевода строки преобразуются на выходе в сочетания символов возврата каретки и перевода строки.  Кроме того, при вводе символ CTRL\+Z интерпретируется как символ конца файла.  В файлах, открытых для чтения или для чтения и записи с `"a+"`, библиотека времени выполнения проверяет на CTRL\+Z в конце файла и удаляет его, если это возможно.  Это делается потому, что использование `fseek` и `ftell` для перемещения в файле, может вызвать неправильное поведение `fseek` ближе к концу файла.  Параметр `t` представляет собой расширение Microsoft и не должен использоваться, если требуется обеспечить переносимость ANSI.  
  
 `b`  
 Открытие файла в бинарном \(непреобразованном\) режиме; вышеописанные преобразования отключены.  
  
 Если символ `t` или `b` в параметре `mode` не указан, режим преобразования по умолчанию определяется глобальной переменной [\_fmode](../../c-runtime-library/fmode.md).  Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`.  
  
 Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод\-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`freopen`|\<stdio.h\>|  
|`_wfreopen`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_freopen.c  
// compile with: /W3  
// This program reassigns stderr to the file  
// named FREOPEN.OUT and writes a line to that file.  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   // Reassign "stderr" to "freopen.out":   
   stream = freopen( "freopen.out", "w", stderr ); // C4996  
   // Note: freopen is deprecated; consider using freopen_s instead  
  
   if( stream == NULL )  
      fprintf( stdout, "error on freopen\n" );  
   else  
   {  
      fprintf( stdout, "successfully reassigned\n" ); fflush( stdout );  
      fprintf( stream, "This will go to the file 'freopen.out'\n" );  
      fclose( stream );  
   }  
   system( "type freopen.out" );  
}  
```  
  
  **successfully reassigned**  
**This will go to the file 'freopen.out'**   
## Эквивалент в .NET Framework  
  
-   <xref:System.IO.File.Open%2A>  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [\_fileno](../Topic/_fileno.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)