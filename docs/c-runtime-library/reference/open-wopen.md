---
title: "_open, _wopen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _open
- _wopen
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
- _wopen
- _topen
- _open
dev_langs:
- C++
helpviewer_keywords:
- opening files, for file I/O
- topen function
- _open function
- _topen function
- _wopen function
- files [C++], opening
- wopen function
- open function
ms.assetid: 13f6a0c3-d1aa-450d-a7aa-74abc91b163e
caps.latest.revision: 31
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 82b12ebfbff06c19a863bec7d8be2e6677c0148e
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="open-wopen"></a>_open, _wopen
Открывает файл. Эти функции являются устаревшими, так как доступны более надежные и безопасные версии. См. описание [_sopen_s, _wsopen_s](../../c-runtime-library/reference/sopen-s-wsopen-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _open(  
   const char *filename,  
   int oflag [,  
   int pmode]   
);  
int _wopen(  
   const wchar_t *filename,  
   int oflag [,  
   int pmode]   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя файла.  
  
 `oflag`  
 Разрешенные типы операций.  
  
 `pmode`  
 Режим разрешений.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает дескриптор файла для открытого файла. Возвращаемое значение -1 указывает на ошибку; в этом случае для `errno` задается одно из следующих значений.  
  
 `EACCES`  
 Попытка открыть для записи файл, доступный только для чтения; запрет указанных операций режимом общего доступа к файлу или "данный путь является каталогом".  
  
 `EEXIST`  
Указаны флаги  `_O_CREAT` и `_O_EXCL`, однако `filename` уже существует.  
  
 `EINVAL`  
 Недопустимый аргумент `oflag` или `pmode`.  
  
 `EMFILE`  
 Больше нет доступных дескрипторов файлов (открыто слишком много файлов).  
  
 `ENOENT`  
 Файл или путь не найден.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `_open` открывает файл, указанный параметром `filename`, и готовит его к чтению или записи, как задано параметром `oflag`. `_wopen` — это версия `_open` с расширенными символами; аргумент `filename` для `_wopen` — строка расширенных символов. Поведение `_wopen` и `_open` идентично в противном случае.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_topen`|`_open`|`_open`|`_wopen`|  
  
 `oflag` является целочисленным выражением, сформированным на базе одной или нескольких следующих констант манифеста или их сочетаний, которые определяются в \<fcntl.h>.  
  
 `_O_APPEND`  
 Перемещает указатель файла в конец файла перед каждой операцией записи.  
  
 `_O_BINARY`  
 Открывает файл в двоичном режиме (без преобразования). (Описание двоичного режима см. в разделе [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_CREAT`  
 Создает файл и открывает его для записи. Не действует, если существует файл, указанный параметром `filename`. Аргумент `pmode` обязателен, если указан флаг `_O_CREAT`.  
  
 `_O_CREAT` &#124; `_O_SHORT_LIVED`  
 Создает файл в качестве временного файла и, по возможности, не сбрасывает его на диск. Аргумент `pmode` обязателен, если указан флаг `_O_CREAT`.  
  
 `_O_CREAT` &#124; `_O_TEMPORARY`  
 Создает файл в качестве временного файла; файл удаляется при закрытии последнего дескриптора файла. Аргумент `pmode` обязателен, если указан флаг `_O_CREAT`.  
  
 `_O_CREAT` &#124; `_O_EXCL`  
 Возвращает значение ошибки, если файл, указанный параметром `filename`, существует. Применяется только при использовании с `_O_CREAT`.  
  
 `_O_NOINHERIT`  
 Предотвращает создание общего дескриптора файла.  
  
 `_O_RANDOM`  
 Указывает, что кэширование оптимизировано для случайного доступа с диска, но не ограничивается им.  
  
 `_O_RDONLY`  
 Открывает файл только для чтения. Нельзя указывать с `_O_RDWR` или `_O_WRONLY`.  
  
 `_O_RDWR`  
 Открывает файл для чтения и записи. Нельзя указывать с `_O_RDONLY` или `_O_WRONLY`.  
  
 `_O_SEQUENTIAL`  
 Указывает, что кэширование оптимизировано для последовательного доступа с диска, но не ограничивается им.  
  
 `_O_TEXT`  
 Открывает файл в текстовом режиме (с преобразованием). (Дополнительные сведения см. в разделах [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md) и [fopen](../../c-runtime-library/reference/fopen-wfopen.md).)  
  
 `_O_TRUNC`  
 Открывает файл и обрезает его до нулевой длины; необходимо разрешение на запись в файл. Нельзя указывать с `_O_RDONLY`. `_O_TRUNC` при использовании с `_O_CREAT` открывает существующий файл или создает новый.  
  
> [!NOTE]
>  Флаг `_O_TRUNC` удаляет содержимое указанного файла.  
  
 `_O_WRONLY`  
 Открывает файл только для записи. Нельзя указывать с `_O_RDONLY` или `_O_RDWR`.  
  
 `_O_U16TEXT`  
 Открывает файл в режиме Юникода UTF-16.  
  
 `_O_U8TEXT`  
 Открывает файл в режиме Юникода UTF-8.  
  
 `_O_WTEXT`  
 Открывает файл в режиме Юникода.  
  
 Чтобы указать режим доступа к файлу, необходимо задать `_O_RDONLY`, `_O_RDWR` или `_O_WRONLY`. Для режима доступа нет значения по умолчанию.  
  
 Если для открытия файла для чтения используется флаг `_O_WTEXT`, `_open` считывает начало файла и проверяет наличие метки порядка байтов (BOM). Если метка есть, файл обрабатывается как UTF-8 или UTF-16LE, в зависимости от значения метки. Если метка порядка байтов есть, файл обрабатывается как ANSI. Если файл открыт для записи с помощью флага `_O_WTEXT`, используется кодировка UTF-16. Независимо от любых предыдущих параметров или метки порядка байтов, если используется флаг `_O_U8TEXT`, файл всегда открывается в кодировке UTF-8; если используется флаг `_O_U16TEXT`, файл всегда открывается в кодировке UTF-16.  
  
 Если файл открывается в режиме Юникода с помощью флагов `_O_WTEXT`, `_O_U8TEXT` или `_O_U16TEXT`, функции ввода преобразуют данные, считываемые из файла в данные UTF-16, хранимые с типом `wchar_t`. Затем функции, которые выполняют запись в файл, открытый в режиме Юникода, ожидают буферы, содержащие данные UTF-16, хранимые с типом `wchar_t`. Если кодировка файла — UTF-8, при его записи данные UTF-16 преобразуются в UTF-8, а содержимое файла с кодировкой UTF-8 преобразуется в данные UTF-16 при его считывании. Попытка чтения или записи нечетного числа байт в режиме Юникода приводит к возникновению ошибки проверки параметра. Для чтения или записи данных, хранимых в программе в кодировке UTF-8, используйте режим текстового или двоичного файла вместо режима Юникода. Вам необходимо реализовать все обязательные преобразования кодировки.  
  
 Если `_open` вызывается с флагами `_O_WRONLY|_O_APPEND` (режим добавления) и `_O_WTEXT`, `_O_U16TEXT` или `_O_U8TEXT`, сначала выполняется попытка открыть файл для чтения и записи, считывается метка порядка байтов, а затем файл снова открывается только для записи. Если происходит сбой открытия файла для чтения и записи, файл открывается только для записи и для параметра режима Юникода используется значение по умолчанию.  
  
 Если несколько констант манифеста используются для формирования аргумента `oflag`, константы объединяются с помощью битового оператора ИЛИ (`|`). Сведения о двоичном и текстовом режимах см. в разделе [Файловый ввод-вывод в текстовом и двоичном режиме](../../c-runtime-library/text-and-binary-mode-file-i-o.md).  
  
 Аргумент `pmode` обязателен, только если указан флаг `_O_CREAT`. Если файл уже существует, `pmode` игнорируется. В противном случае аргумент `pmode` задает параметры разрешений файла, которые настраиваются при первом закрытии нового файла. `_open` применяет текущую маску разрешений файла к `pmode` до настройки разрешений. (Дополнительные сведения см. в разделе [_umask](../../c-runtime-library/reference/umask.md).) `pmode` — это целочисленное выражение, которое содержит одну или несколько следующих констант манифеста, определяемых в \<sys\stat.h>.  
  
 `_S_IREAD`  
 Разрешено только чтение.  
  
 `_S_IWRITE`  
 Разрешена запись. (Если действует, разрешает чтение и запись.)  
  
 `_S_IREAD`  `|`  `_S_IWRITE`  
 Разрешены чтение и запись.  
  
 Если заданы обе константы, они соединяются с помощью битового оператора ИЛИ ( `|` ). В Windows все файлы доступны для чтения; разрешение только на запись недоступно. Поэтому режимы `_S_IWRITE` и `_S_IREAD` `|` `_S_IWRITE` эквивалентны.  
  
 Если для аргумента `pmode` указано значение, отличающееся от некоего сочетания `_S_IREAD` и `_S_IWRITE` (даже если оно задает допустимое значение `pmode` в другой операционной системе) или если указано любое значение, кроме разрешенных значений `oflag`, функция создает утверждение в режиме отладки и вызывает обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, функция возвращает -1 и устанавливает `errno` в значение `EINVAL`.  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательный заголовок|  
|-------------|---------------------|---------------------|  
|`_open`|\<io.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|  
|`_wopen`|\<io.h> или \<wchar.h>|\<fcntl.h>, \<sys\types.h>, \<sys\stat.h>|  
  
 `_open` и `_wopen` являются расширениями Майкрософт. Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Библиотеки  
 Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Пример  
  
```  
// crt_open.c  
// compile with: /W3  
/* This program uses _open to open a file  
 * named CRT_OPEN.C for input and a file named CRT_OPEN.OUT  
 * for output. The files are then closed.  
 */  
#include <fcntl.h>  
#include <sys/types.h>  
#include <sys/stat.h>  
#include <io.h>  
#include <stdio.h>  
  
int main( void )  
{  
   int fh1, fh2;  
  
   fh1 = _open( "CRT_OPEN.C", _O_RDONLY ); // C4996  
   // Note: _open is deprecated; consider using _sopen_s instead  
   if( fh1 == -1 )  
      perror( "Open failed on input file" );  
   else  
   {  
      printf( "Open succeeded on input file\n" );  
      _close( fh1 );  
   }  
  
   fh2 = _open( "CRT_OPEN.OUT", _O_WRONLY | _O_CREAT, _S_IREAD |   
                            _S_IWRITE ); // C4996  
   if( fh2 == -1 )  
      perror( "Open failed on output file" );  
   else  
   {  
      printf( "Open succeeded on output file\n" );  
      _close( fh2 );  
   }  
}  
```  
  
## <a name="output"></a>Вывод  
  
```  
Open succeeded on input file  
Open succeeded on output file  
```  
  
## <a name="see-also"></a>См. также  
 [Низкоуровневый ввод-вывод](../../c-runtime-library/low-level-i-o.md)   
 [_chmod, _wchmod](../../c-runtime-library/reference/chmod-wchmod.md)   
 [_close](../../c-runtime-library/reference/close.md)   
 [_creat, _wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [_dup, _dup2](../../c-runtime-library/reference/dup-dup2.md)   
 [fopen, _wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)
