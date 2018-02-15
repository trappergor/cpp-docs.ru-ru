---
title: "_fsopen, _wfsopen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- _wfsopen
- _fsopen
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
- wfsopen
- fsopen
- tfsopen
- _tfsopen
- _wfsopen
- _fsopen
dev_langs:
- C++
helpviewer_keywords:
- opening files, streams
- fsopen function
- tfsopen function
- wfsopen function
- _fsopen function
- files [C++], opening
- _tfsopen function
- _wfsopen function
- file sharing [C++]
ms.assetid: 5e4502ab-48a9-4bee-a263-ebac8d638dec
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 29ace593ec55a74db72a9bfd9d8f155055923a83
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="fsopen-wfsopen"></a>_fsopen, _wfsopen
Открывает поток с совместным доступом к файлу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FILE *_fsopen(   
   const char *filename,  
   const char *mode,  
   int shflag   
);  
FILE *_wfsopen(   
   const wchar_t *filename,  
   const wchar_t *mode,  
   int shflag   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя файла, который необходимо открыть.  
  
 `mode`  
 Тип разрешенного доступа.  
  
 `shflag`  
 Разрешенный тип общего доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на поток. Значение указателя null обозначает ошибку. Если параметр `filename` или `mode` имеет значение `NULL` или является пустой строкой, эти функции вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции возвращают `NULL` и устанавливают для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist, and _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_fsopen` открывает файл, указанный в параметре `filename`, в качестве потока и готовит файл для последующих операций чтения или записи с общим доступом, как определено режимом и аргументами `shflag`. `_wfsopen` — это версия функции `_fsopen` для расширенных символов; аргументы `filename` и `mode` для функции `_wfsopen` представляют собой строки расширенных символов. Поведение `_wfsopen` и `_fsopen` идентично в противном случае.  
  
 Символьная строка `mode` указывает тип доступа, запрошенный для файла, как показано в следующей таблице.  
  
|Термин|Определение|  
|----------|----------------|  
|`"r"`|Открывает для чтения. Если файл не существует или его невозможно найти, вызов `_fsopen` завершается ошибкой.|  
|`"w"`|Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.|  
|`"a"`|Открывает для записи в конец файла (добавление); сначала создает файл, если он не существует.|  
|`"r+"`|Открывает для чтения и записи. (Файл должен существовать.)|  
|`"w+"`|Открывает пустой файл для чтения и записи. Если указанный файл существует, его содержимое удаляется.|  
|`"a+"`|Открывает для чтения и добавления; сначала создает файл, если он не существует.|  
  
 Используйте типы `"w"` и `"w+"` с осторожностью, поскольку они могут приводить к уничтожению существующих файлов.  
  
 Если файл открыт с помощью типа доступа `"a"` или `"a+"`, все операции записи выполняются в конце файла. Указатель файла можно перемещать с помощью функции `fseek` или `rewind`, но он всегда возвращается в конец файла перед выполнением любой операции записи. Поэтому перезаписать существующие данные невозможно. Если задан тип доступа `"r+"`, `"w+"` или `"a+"`, чтение и запись разрешены (считается, что файл открыт для обновления). Однако при переключении между чтением и записью необходима промежуточная операция [fsetpos](../../c-runtime-library/reference/fsetpos.md), [fseek](../../c-runtime-library/reference/fseek-fseeki64.md) или [rewind](../../c-runtime-library/reference/rewind.md). При необходимости для операции `fsetpos` или `fseek` можно задать текущее положение. Помимо вышеуказанных значений, в параметр `mode` можно включить один из следующих символов для определения режима преобразования новых строк, а также для управления файлами.  
  
|Термин|Определение|  
|----------|----------------|  
|`t`|Открывает файл в текстовом режиме (с преобразованием). В этом режиме каретки возврат строки веб-канала (CR-LF) преобразуются в веб-каналы одной строки (LF) на входе и символы перевода строки преобразуются на выходе в сочетания возврата каретки. Кроме того, при вводе символ CTRL+Z интерпретируется как символ конца файла. В файлах, открытых для чтения или чтения/записи, функция `_fsopen` проверяет наличие символа CTRL+Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование функции `fseek` и `ftell` для перемещения в файле, который заканчивается символом CTRL+Z, может вызвать неправильное поведение `fseek` вблизи конца файла.|  
|`b`|Открывает файл в двоичном (непреобразованном) режиме; вышеописанные преобразования отключены.|  
|`S`|Указывает, что кэширование оптимизировано для последовательного доступа с диска, но не ограничивается им.|  
|`R`|Указывает, что кэширование оптимизировано для случайного доступа с диска, но не ограничивается им.|  
|`T`|Определяет файл как временный. По возможности он не сбрасывается на диск.|  
|`D`|Определяет файл как временный. Он удаляется, если закрывается последний указатель файла.|  
  
 Если `t` или `b` не указаны в параметре `mode`, режим преобразования определяется переменной режима по умолчанию `_fmode`. Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`. Обсуждение текстового и двоичного режимов см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Аргумент `shflag` — это константное выражение, которое состоит из одной из следующих констант манифеста, определенных в share.h.  
  
|Термин|Определение|  
|----------|----------------|  
|`_SH_COMPAT`|Задает режим совместимости для 16 разрядных приложений.|  
|`_SH_DENYNO`|Разрешает доступ на чтение и запись.|  
|`_SH_DENYRD`|Запрещает доступ к файлу для чтения.|  
|`_SH_DENYRW`|Запрещает доступ к файлу для чтения и записи.|  
|`_SH_DENYWR`|Запрещает доступ к файлу для записи.|  
  
### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_tfsopen`|`_fsopen`|`_fsopen`|`_wfsopen`|  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|Необязательные заголовки|  
|--------------|---------------------|----------------------|  
|`_fsopen`|\<stdio.h>|\<share.h><br /><br /> Для константы манифеста для параметра `shflag`.|  
|`_wfsopen`|\<stdio.h> или \<wchar.h>|\<share.h><br /><br /> Для константы манифеста для параметра `shflag`.|  
  
## <a name="example"></a>Пример  
  
```  
// crt_fsopen.c  
  
#include <stdio.h>  
#include <stdlib.h>  
#include <share.h>  
  
int main( void )  
{  
   FILE *stream;  
  
   // Open output file for writing. Using _fsopen allows us to  
   // ensure that no one else writes to the file while we are  
   // writing to it.  
    //  
   if( (stream = _fsopen( "outfile", "wt", _SH_DENYWR )) != NULL )  
   {  
      fprintf( stream, "No one else in the network can write "  
                       "to this file until we are done.\n" );  
      fclose( stream );  
   }  
   // Now others can write to the file while we read it.  
   system( "type outfile" );  
}  
```  
  
```Output  
No one else in the network can write to this file until we are done.  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)