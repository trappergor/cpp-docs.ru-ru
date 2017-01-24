---
title: "freopen_s, _wfreopen_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wfreopen_s"
  - "freopen_s"
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
  - "freopen_s"
  - "_tfreopen_s"
  - "_wfreopen_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_tfreopen_s - функция"
  - "_wfreopen_s - функция"
  - "указатели файлов [C++], повторное назначение"
  - "freopen_s - функция"
  - "tfreopen_s - функция"
  - "wfreopen_s - функция"
ms.assetid: ad25a4da-6ad4-476b-a86d-660b221ca84d
caps.latest.revision: 27
caps.handback.revision: 25
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# freopen_s, _wfreopen_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Переназначает указатель файла.  Это версии функций [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md) с повышенной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
errno_t freopen(   
   FILE** pFile,  
   const char *path,  
   const char *mode,  
   FILE *stream   
);  
errno_t _wfreopen(   
   FILE** pFile,  
   const wchar_t *path,  
   const wchar_t *mode,  
   FILE *stream   
);  
```  
  
#### Параметры  
 \[выходной\] `pFile`  
 Указатель на указатель файла, который будет предоставлен вызовом.  
  
 \[in\] `path`  
 Путь к новому файлу.  
  
 \[in\] `mode`  
 Тип разрешенного доступа.  
  
 \[in\] `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает код ошибки.  При возникновении ошибки исходный файл закрывается.  
  
## Заметки  
 Функция `freopen_s` закрывает файл, связанный в данный момент с `stream`, и связывает `stream` с файлом, указанным аргументом `path.` `_wfreopen_s` является версией `_freopen_s` с расширенными символами; аргументы `path` и `mode` в `_wfreopen_s` — строки расширенных символов.  Поведение `_wfreopen_s` и `_freopen_s` идентично в противном случае.  
  
 Если любой из аргументов `pFile`, `path`, `mode` или `stream` равен `NULL` или если `path` является пустой строкой, эти функции активируют обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `EINVAL`.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tfreopen_s`|`freopen_s`|`freopen_s`|`_wfreopen_s`|  
  
 `freopen_s` обычно используется для перенаправления заранее открытых файлов `stdin`, `stdout` и `stderr` на файлы, определенные пользователем.  Новый файл, связанный с `stream`, открывается с `mode`*,* — символьной строкой, указывающей запрошенный тип доступа для файла, следующим образом:  
  
 `"r"`  
 Открывает для чтения.  Если файл не существует или его невозможно найти, вызов `freopen_s` завершается ошибкой.  
  
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
  
 Если задан тип доступа `"r+",`, `"w+",` или `"a+"`, разрешены и чтение, и запись \(считается, что файл открыт для обновления\).  Однако при переключении между чтением и записью необходимо выполнить промежуточную операцию [fsetpos](../Topic/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) или [rewind](../../c-runtime-library/reference/rewind.md).  При необходимости для операции `fsetpos` или `fseek` можно задать текущее положение.  Помимо вышеуказанных значений один из следующих символов может быть включен в строку `mode` для определения режима преобразования новых строк.  
  
 `t`  
 Открыть в текстовом режиме \(преобразование\); сочетания символов возврата каретки и перевода строки преобразуются в один символ перевода строки на входе, а символы перевода строки преобразуются на выходе в сочетания символов возврата каретки и перевода строки.  Кроме того, при вводе символ CTRL\+Z интерпретируется как символ конца файла.  В файлах, открытых для чтения или для чтения и записи с `"a+"`, библиотека времени выполнения проверяет на CTRL\+Z в конце файла и удаляет его, если это возможно.  Это делается потому, что использование `fseek` и `ftell` для перемещения в файле, может вызвать неправильное поведение `fseek` ближе к концу файла.  Параметр `t` представляет собой расширение Microsoft и не должен использоваться, если требуется обеспечить переносимость ANSI.  
  
 `b`  
 Открытие файла в бинарном \(непреобразованном\) режиме; вышеописанные преобразования отключены.  
  
 Если символ `t` или `b` в параметре `mode` не указан, режим преобразования по умолчанию определяется глобальной переменной [\_fmode](../../c-runtime-library/fmode.md).  Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`.  
  
 Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод\-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## Требования  
  
|Функция|Обязательный заголовок|  
|-------------|----------------------------|  
|`freopen_s`|\<stdio.h\>|  
|`_wfreopen_s`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_freopen_s.c  
// This program reassigns stderr to the file  
// named FREOPEN.OUT and writes a line to that file.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
FILE *stream;  
  
int main( void )  
{  
   errno_t err;  
   // Reassign "stderr" to "freopen.out":   
   err = freopen_s( &stream, "freopen.out", "w", stderr );  
  
   if( err != 0 )  
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
  
-   [System::IO::File::Open](https://msdn.microsoft.com/en-us/library/system.io.file.open.aspx)  
  
-   <xref:System.IO.FileStream.%23ctor%2A>  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [freopen, \_wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [fclose, \_fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [\_fdopen, \_wfdopen](../Topic/_fdopen,%20_wfdopen.md)   
 [\_fileno](../Topic/_fileno.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_setmode](../../c-runtime-library/reference/setmode.md)