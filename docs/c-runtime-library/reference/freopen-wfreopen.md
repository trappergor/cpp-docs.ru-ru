---
title: "freopen, _wfreopen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- freopen
- _wfreopen
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
- _wfreopen
- _tfreopen
- freopen
dev_langs:
- C++
helpviewer_keywords:
- _wfreopen function
- file pointers [C++], reassigning
- _tfreopen function
- freopen function
- tfreopen function
- wfreopen function
ms.assetid: de4b73f8-1043-4d62-98ee-30d2022da885
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 47b45dd9e2ad07032529652021172ea64b84d652
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="freopen-wfreopen"></a>freopen, _wfreopen
Переназначает указатель файла. Существуют более безопасные версии этих функций; см. раздел [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `path`  
 Путь к новому файлу.  
  
 `mode`  
 Тип разрешенного доступа.  
  
 `stream`  
 Указатель на структуру `FILE` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на вновь открытый файл. Если возникает ошибка, исходный файл закрывается, а функция возвращает значение указателя `NULL`. Если параметр `path`, `mode` или `stream` является указателем NULL либо `filename` является пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, эти функции устанавливают параметр `errno` в значение `EINVAL` и возвращают значение `NULL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Существуют более безопасные версии этих функций; см. раздел [freopen_s, _wfreopen_s](../../c-runtime-library/reference/freopen-s-wfreopen-s.md).  
  
 `freopen` Функция закрывает файл, который сейчас связан с `stream` и переназначает `stream` в файл, заданный параметром `path`. `_wfreopen` — это версия функции `_freopen` для расширенных символов; аргументы `path` и `mode` для функции `_wfreopen` представляют собой строки расширенных символов. Поведение `_wfreopen` и `_freopen` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfreopen`|`freopen`|`freopen`|`_wfreopen`|  
  
 `freopen` обычно используется для перенаправления заранее открытых файлов `stdin`, `stdout` и `stderr` на файлы, определенные пользователем. Новый файл, связанный с `stream` открывается с `mode`, который представляет собой строку символов, указывающие тип доступа, запрошенный для файла, следующим образом:  
  
 `"r"`  
 Открывает для чтения. Если файл не существует или его невозможно найти, вызов `freopen` завершается ошибкой.  
  
 `"w"`  
 Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.  
  
 `"a"`  
 Открывает для записи в конце файла (добавление) без удаления маркера конца файла перед записью новых данных в файл; создает файл, если он не существует.  
  
 `"r+"`  
 Открывает для чтения и записи. (Файл должен существовать.)  
  
 `"w+"`  
 Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.  
  
 `"a+"`  
 Открывает для чтения и добавления; операция добавления включает в себя удаление маркера конца файла перед записью новых данных в файл и восстановление маркера конца файла после завершения записи; создает файл, если он не существует.  
  
 Используйте типы `"w"` и `"w+"` с осторожностью, поскольку они могут приводить к уничтожению существующих файлов.  
  
 Если файл открывается с помощью типа доступа `"a"` или `"a+"`, все операции записи выполняются в конце файла. Хотя указатель файла может быть перемещен с помощью `fseek` или `rewind`, он всегда возвращается в конец файла перед выполнением любой операции записи. Поэтому перезаписать существующие данные невозможно.  
  
 Режим `"a"` не удаляет маркер конца файла перед добавлением в файл. После добавления команда MS-DOS TYPE отображает данные только до первоначального маркера EOF и не отображает данные, добавленные в файл. Перед добавлением в файл режим `"a+"` удаляет маркер конца файла. После добавления команда TYPE MS-DOS отображает все данные в файле. Режим `"a+"` необходим для добавления в потоковый файл, завершаемый маркером конца файла CTRL+Z.  
  
 Если задан тип доступа `"r+"`, `"w+"` или `"a+"`, чтение и запись разрешены (считается, что файл открыт для "обновления"). Однако при переключении между чтением и записью необходимо выполнить промежуточную операцию [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) или [rewind](../../c-runtime-library/reference/rewind.md). При необходимости для операции `fsetpos` или `fseek` можно задать текущее положение. Помимо вышеуказанных значений один из следующих символов может быть включен в строку `mode` для определения режима преобразования новых строк.  
  
 `t`  
 Откройте файл в текстовом (переведенном) режиме; каретки return-перевода строки (CR-LF) преобразуются в символы одной перевода строки (LF) во входных данных; Символы перевода строки преобразуются на выходе в сочетания возврата каретки. Кроме того, при вводе символ CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или для чтения и записи с `"a+"`, библиотека времени выполнения проверяет на CTRL+Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование `fseek` и `ftell` для перемещения в файле, может вызвать неправильное поведение `fseek` ближе к концу файла. Параметр `t` представляет собой расширение Microsoft и не должен использоваться, если требуется обеспечить переносимость ANSI.  
  
 `b`  
 Открытие файла в бинарном (непреобразованном) режиме; вышеописанные преобразования отключены.  
  
 Если символ `t` или `b` в параметре `mode` не указан, режим преобразования по умолчанию определяется глобальной переменной [_fmode](../../c-runtime-library/fmode.md). Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`.  
  
 Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`freopen`|\<stdio.h>|  
|`_wfreopen`|\<stdio.h> или \<wchar.h>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="example"></a>Пример  
  
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
  
```Output  
successfully reassigned  
This will go to the file 'freopen.out'  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)
