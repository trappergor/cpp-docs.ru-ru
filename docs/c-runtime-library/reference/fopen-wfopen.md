---
title: "fopen, _wfopen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wfopen
- fopen
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
- fopen
- _wfopen
- _tfopen
- corecrt_wstdio/_wfopen
- stdio/fopen
dev_langs: C++
helpviewer_keywords:
- opening files, for file I/O
- wfopen function
- tfopen function
- _tfopen function
- _wfopen function
- files [C++], opening
- fopen function
ms.assetid: e868993f-738c-4920-b5e4-d8f2f41f933d
caps.latest.revision: "56"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: c5a81cdcba10d65c496a946fb8847fdb09b1ff70
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fopen-wfopen"></a>fopen, _wfopen
Открывает файл. Доступны более надежные и безопасные версии этих функций, выполняющие дополнительные проверки параметров и возвращающие коды ошибок. См. [fopen_s, _wfopen_s](../../c-runtime-library/reference/fopen-s-wfopen-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
FILE *fopen(   
   const char *filename,  
   const char *mode   
);  
FILE *_wfopen(   
   const wchar_t *filename,  
   const wchar_t *mode   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `filename`  
 Имя файла.  
  
 `mode`  
 Включенный тип доступа.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает указатель на открытый файл. Значение указателя null обозначает ошибку. Если `filename` или `mode` равно `NULL` или является пустой строкой, эти функции активируют обработчик недопустимых параметров, как описано в статье [Parameter Validation](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции возвращают `NULL` и устанавливают для `errno` значение `EINVAL`.  
  
 Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `fopen` открывает файл, заданный `filename`. По умолчанию узкая строка `filename` интерпретируется с использованием кодовой страницы ANSI (CP_ACP). В классических приложениях Windows эту страницу можно изменить на кодовую страницу OEM (CP_OEMCP) с помощью функции [SetFileApisToOEM](https://msdn.microsoft.com/library/windows/desktop/aa365534\(v=vs.85\).aspx) . Функцию [AreFileApisANSI](https://msdn.microsoft.com/library/windows/desktop/aa363781\(v=vs.85\).aspx) можно использовать для определения, интерпретируется ли `filename` с использованием кодовой страницы ANSI или кодовой страницы OEM системы по умолчанию. `_wfopen` — это двухбайтовая версия `fopen`; аргументы для `_wfopen` представляют собой двухбайтовые строки. В противном случае поведение `_wfopen` и `fopen` идентично. Использование исключительно `_wfopen` не влияет на набор закодированных символов, используемый в файловом потоке.  
  
 `fopen` принимает пути, допустимые в файловой системе, в точке выполнения; `fopen` принимает UNC-пути и пути, содержащие сопоставленные сетевые диски, если выполняющая код система имеет доступ к общей папке или сопоставленному диску во время выполнения. При построении путей для `fopen`убедитесь, что драйверы, пути или сетевые общие папки будут доступны в среде выполнения. В пути в качестве разделителей каталогов можно использовать прямую (/) или обратную (\\) косую черту.  
  
 Всегда проверяйте возвращаемое значение, чтобы узнать, равен ли указатель NULL, прежде чем выполнять какие-либо дальнейшие операции с файлом. При возникновении ошибки задается глобальная переменная `errno` , которая может использоваться для получения конкретных сведений об ошибке. Дополнительные сведения см. в разделе [errno, _doserrno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="unicode-support"></a>Поддержка Юникода  
 `fopen` поддерживает файловые потоки Юникода. Чтобы открыть файл Юникода, передайте флаг `ccs` , задающий нужную кодировку, в `fopen`следующим образом.  
  
 `FILE *fp = fopen("newfile.txt", "rt+, ccs=encoding");`  
  
 Допустимые значения `encoding` — `UNICODE`, `UTF-8`и `UTF-16LE`.  
  
 Если файл открывается в режиме Юникода, функции ввода преобразуют данные, считываемые из файла в данные UTF-16, хранимые с типом `wchar_t`. Затем функции, которые выполняют запись в файл, открытый в режиме Юникода, ожидают буферы, содержащие данные UTF-16, хранимые с типом `wchar_t`. Если кодировка файла — UTF-8, при его записи данные UTF-16 преобразуются в UTF-8, а содержимое файла с кодировкой UTF-8 преобразуется в данные UTF-16 при его считывании. Попытка чтения или записи нечетного числа байт в режиме Юникода приводит к возникновению ошибки [проверки параметра](../../c-runtime-library/parameter-validation.md) . Для чтения или записи данных, хранимых в программе в кодировке UTF-8, используйте режим текстового или двоичного файла вместо режима Юникода. Вам необходимо реализовать все обязательные преобразования кодировки.  
  
 Если файл уже существует и открыт для чтения или добавления, метка порядка байтов (BOM), если она присутствует в файле, определяет кодирование. Кодирование BOM имеет приоритет над кодированием, заданным флагом `ccs` . Кодирование `ccs` используется, только если метка BOM отсутствует или речь идет о новом файле.  
  
> [!NOTE]
>  Обнаружение метки BOM применяется только к файлам, которые будут открываться в режиме Юникода (т е путем передачи флага `ccs` ).  
  
 В следующей таблице приведены режимы, которые используются для различных флагов `ccs` , присвоенных `fopen` и метка порядка байтов в файле.  
  
### <a name="encodings-used-based-on-ccs-flag-and-bom"></a>Кодирования, используемые на основе CCS-флага и метки BOM  
  
|Флаг`ccs` |Нет метки BOM (или новый файл)|BOM: UTF-8|BOM: UTF-16|  
|----------------|----------------------------|-----------------|------------------|  
|`UNICODE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
|`UTF-8`|`UTF-8`|`UTF-8`|`UTF-16LE`|  
|`UTF-16LE`|`UTF-16LE`|`UTF-8`|`UTF-16LE`|  
  
 В файлы, открытые для записи в режиме Юникода, метка BOM записывается автоматически.  
  
 Если `mode` —`a, ccs=<encoding>`, то `fopen` сначала пытается открыть файл с правами на чтение и доступ. Если это завершается успешно, функция считывает метку BOM, чтобы определить кодировку для файла; если операция завершается сбоем, функция использует для файла кодировку по умолчанию. В любом случае `fopen` затем снова открывает файл с правами только на запись. (Это актуально только для режима `a` , а не `a+` ).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tfopen`|`fopen`|`fopen`|`_wfopen`|  
  
 Символьная строка `mode` указывает тип доступа, который запрошен для файла, следующим образом.  
  
 `"r"`  
 Открывает для чтения. Если файл не существует или его невозможно найти, вызов `fopen` завершается ошибкой.  
  
 `"w"`  
 Открывает пустой файл для записи. Если указанный файл существует, его содержимое удаляется.  
  
 `"a"`  
 Открывается для записи в конце файла (добавление) без удаления маркера в конце файла (EOF) перед записью новых данных в файл. Создает файл, если он не существует.  
  
 `"r+"`  
 Открывает для чтения и записи. Файл должен существовать.  
  
 `"w+"`  
 Открывает пустой файл для чтения и записи. Если файл существует, его содержимое удаляется.  
  
 `"a+"`  
 Открывается для чтения и добавления. Операция добавления включает удаления маркера EOF перед записью новых данных в файл. Маркер EOF не восстанавливается по окончании записи. Создает файл, если он не существует.  
  
 Если файл открывается с помощью типа доступа `"a"` или `"a+"` , все операции записи выполняются в конце файла. Указатель файла может быть перемещен с помощью `fseek` или `rewind`, но он всегда возвращается в конец файла перед выполнением любой операции записи. Поэтому невозможно перезаписать существующие данные.  
  
 Режим `"a"` не удаляет маркер EOF, прежде чем будет выполнено добавление в файл. После добавления команда MS-DOS TYPE отображает данные только до первоначального маркера EOF и не отображает данные, добавленные в файл. Перед добавлением в файл режим `"a+"` удаляет маркер EOF. После добавления команда TYPE MS-DOS отображает все данные в файле. Режим `"a+"` необходим для добавления в потоковый файл, завершаемый маркером конца файла CTRL+Z.  
  
 Если задан тип доступа `"r+"`, `"w+"`или `"a+"` , чтение и запись разрешены (считается, что файл открыт для обновления). Однако при переходе от чтения к записи операция ввода должна получить маркер конца файла. Если маркер EOF отсутствует, необходимо воспользоваться промежуточным вызовом функции размещения файла. Функции размещения файла — `fsetpos`, `fseek`и `rewind`. При переходе от записи к чтению необходимо воспользоваться промежуточным вызовом функции `fflush` или функции размещения файла.  
  
 В дополнение к указанным ранее значениям можно добавить в `mode` следующие символы, чтобы задать режим перевода для символов новой строки.  
  
 `t`  
 Откройте файл в текстовом (переведенном) режиме. В этом режиме CTRL+Z интерпретируется как символ конца файла на входе. В файлах, открытых для чтения или записи с помощью `"a+"`, `fopen` проверяет наличие CTRL + Z в конце файла и удаляет его, если это возможно. Это делается потому, что использование `fseek` и `ftell` для перемещения в файле, который заканчивается CTRL+Z, может вызвать неправильное поведение `fseek` ближе к концу файла.  
  
 В текстовом режиме сочетания символов возврата перевода каретки преобразуются в один символ перевода строки на входе и символы перевода строки преобразуются на выходе в сочетания перевода строки возврата каретки. Если функция ввода-вывода потока Юникода работает в текстовом режиме (по умолчанию) исходный или конечный поток рассматривается как последовательность многобайтовых символов. Поэтому входные функции потока Юникода преобразуют многобайтовые символы в расширенные (как если бы для этого вызывалась функция `mbtowc` ). По той же причине выходные функции потока Юникода преобразуют расширенные символы в многобайтовые (как если бы для этого вызывалась функция `wctomb` ).  
  
 `b`  
 При открытии в двоичном (непреобразованном) режиме преобразования, включающие символы возврата каретки и перевода строки, подавляются.  
  
 Если символ `t` или `b` в параметре `mode`не указан, режим преобразования по умолчанию определяется глобальной переменной [_fmode](../../c-runtime-library/fmode.md). Если символ `t` или `b` указан как префикс аргумента, функция завершается с ошибкой и возвращает `NULL`.  
  
 Дополнительные сведения об использовании текстового и двоичного режимов в Юникоде, а также многобайтового потока ввода-вывода см. в статьях [Text and Binary Mode File I/O](../../c-runtime-library/text-and-binary-mode-file-i-o.md) и [Unicode Stream I/O in Text and Binary Modes](../../c-runtime-library/unicode-stream-i-o-in-text-and-binary-modes.md).  
  
 `c`  
 Включите флажок фиксации для связанного объекта `filename` , чтобы содержимое файлового буфера записывалось непосредственно на диск при вызове `fflush` или `_flushall` .  
  
 `n`  
 Сбросьте флажок фиксации для связанного объекта `filename` , задайте для него значение "без фиксации". Это значение по умолчанию. Оно также переопределяет глобальный флаг фиксации при соединении программы с COMMODE.OBJ. Значение по умолчанию глобального флага фиксации — "без фиксации" (no-commit), если только программа не связана явно с файлом COMMODE.OBJ (см. статью [Link Options](../../c-runtime-library/link-options.md)).  
  
 `N`  
 Указывает, что файл не наследуется дочерними процессами.  
  
 `S`  
 Указывает, что кэширование оптимизировано для последовательного доступа с диска, но не ограничивается им.  
  
 `R`  
 Указывает, что кэширование оптимизировано для случайного доступа с диска, но не ограничивается им.  
  
 `T`  
 Определяет файл как временный. По возможности он не сбрасывается на диск.  
  
 `D`  
 Определяет файл как временный. Он удаляется, если закрывается последний указатель файла.  
  
 `ccs=ENCODING`  
 Задает набор кодированных символов, которые требуется использовать (`UTF-8`, `UTF-16LE`или `UNICODE`) для этого файла. Не указывайте никакое значение, если требуется использовать кодировку ANSI.  
  
 Допустимые символы для строки `mode` , используемой в `fopen` и `_fdopen` , соответствуют аргументам `oflag` , которые используются в [_open](../../c-runtime-library/reference/open-wopen.md) и [_sopen](../../c-runtime-library/reference/sopen-wsopen.md)следующим образом.  
  
|Символы в строке режима|Эквивалентное значение `oflag` для `_open`/`_sopen`|  
|-------------------------------|----------------------------------------------------|  
|`a`|`_O_WRONLY &#124; _O_APPEND` (обычно `_O_WRONLY &#124; _O_CREAT &#124; _O_APPEND`)|  
|`a+`|`_O_RDWR &#124; _O_APPEND` (обычно `_O_RDWR &#124; _O_APPEND &#124; _O_CREAT` )|  
|`r`|`_O_RDONLY`|  
|`r+`|`_O_RDWR`|  
|`w`|`_O_WRONLY` (обычно `_O_WRONLY &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`w+`|`_O_RDWR` (обычно `_O_RDWR &#124; _O_CREAT &#124; _O_TRUNC`)|  
|`b`|`_O_BINARY`|  
|`t`|`_O_TEXT`|  
|`c`|Нет|  
|`n`|Нет|  
|`S`|`_O_SEQUENTIAL`|  
|`R`|`_O_RANDOM`|  
|`T`|`_O_SHORTLIVED`|  
|`D`|`_O_TEMPORARY`|  
|`ccs=UNICODE`|`_O_WTEXT`|  
|`ccs=UTF-8`|`_O_UTF8`|  
|`ccs=UTF-16LE`|`_O_UTF16`|  
  
 Если используется режим `rb` , не нужно портировать код, ожидается, что будет прочитана большая часть крупного файла или производительность сети не играет роли, можно в качестве альтернативы также использовать сопоставленные памяти файлы Win32.  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`fopen`|\<stdio.h>|  
|`_wfopen`|\<stdio.h> или \<wchar.h>|  
  
 `_wfopen` является расширением Майкрософт. Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).  
  
 Параметры `c`, `n`, `t`, `S`, `R`, `T`и `D` `mode` представляют собой расширения Майкрософт для `fopen` и `_fdopen` и should not be used where ANSI portability is desired.  
  
## <a name="example"></a>Пример  
 Следующая программа открывает два файла.  Она использует `fclose` для закрытия первого файла и `_fcloseall` для закрытия всех остальных файлов.  
  
```C  
// crt_fopen.c  
// compile with: /W3  
// This program opens two files. It uses  
// fclose to close the first file and  
// _fcloseall to close all remaining files.  
  
#include <stdio.h>  
  
FILE *stream, *stream2;  
  
int main( void )  
{  
   int numclosed;  
  
   // Open for read (will fail if file "crt_fopen.c" does not exist)  
   if( (stream  = fopen( "crt_fopen.c", "r" )) == NULL ) // C4996  
   // Note: fopen is deprecated; consider using fopen_s instead  
      printf( "The file 'crt_fopen.c' was not opened\n" );  
   else  
      printf( "The file 'crt_fopen.c' was opened\n" );  
  
   // Open for write   
   if( (stream2 = fopen( "data2", "w+" )) == NULL ) // C4996  
      printf( "The file 'data2' was not opened\n" );  
   else  
      printf( "The file 'data2' was opened\n" );  
  
   // Close stream if it is not NULL   
   if( stream)  
   {  
      if ( fclose( stream ) )  
      {  
         printf( "The file 'crt_fopen.c' was not closed\n" );  
      }  
   }  
  
   // All other files are closed:   
   numclosed = _fcloseall( );  
   printf( "Number of files closed by _fcloseall: %u\n", numclosed );  
}  
```  
  
```Output  
The file 'crt_fopen.c' was opened  
The file 'data2' was opened  
Number of files closed by _fcloseall: 1  
```  
  
## <a name="example"></a>Пример  
 Следующая программа создает файл (или перезаписывает его, если имеется) в текстовом режиме с кодировкой Юникода.  Затем она записывает две строки в файл и закрывает его. В результате получается файл с именем _wfopen_test.xml, который содержит данные из раздела вывода.  
  
```C  
// crt__wfopen.c  
// compile with: /W3  
// This program creates a file (or overwrites one if  
// it exists), in text mode using Unicode encoding.  
// It then writes two strings into the file  
// and then closes the file.  
  
#include <stdio.h>  
#include <stddef.h>  
#include <stdlib.h>  
#include <wchar.h>  
  
#define BUFFER_SIZE 50  
  
int main(int argc, char** argv)  
{  
    wchar_t str[BUFFER_SIZE];  
    size_t  strSize;  
    FILE*   fileHandle;  
  
    // Create an the xml file in text and Unicode encoding mode.  
    if ((fileHandle = _wfopen( L"_wfopen_test.xml",L"wt+,ccs=UNICODE")) == NULL) // C4996  
    // Note: _wfopen is deprecated; consider using _wfopen_s instead  
    {  
        wprintf(L"_wfopen failed!\n");  
        return(0);  
    }  
  
    // Write a string into the file.  
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"<xmlTag>\n");  
    strSize = wcslen(str);  
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)  
    {  
        wprintf(L"fwrite failed!\n");  
    }  
  
    // Write a string into the file.  
    wcscpy_s(str, sizeof(str)/sizeof(wchar_t), L"</xmlTag>");  
    strSize = wcslen(str);  
    if (fwrite(str, sizeof(wchar_t), strSize, fileHandle) != strSize)  
    {  
        wprintf(L"fwrite failed!\n");  
    }  
  
    // Close the file.  
    if (fclose(fileHandle))  
    {  
        wprintf(L"fclose failed!\n");  
    }  
    return 0;  
}  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [fclose, _fcloseall](../../c-runtime-library/reference/fclose-fcloseall.md)   
 [_fdopen, _wfdopen](../../c-runtime-library/reference/fdopen-wfdopen.md)   
 [ferror](../../c-runtime-library/reference/ferror.md)   
 [_fileno](../../c-runtime-library/reference/fileno.md)   
 [freopen, _wfreopen](../../c-runtime-library/reference/freopen-wfreopen.md)   
 [_open, _wopen](../../c-runtime-library/reference/open-wopen.md)   
 [_setmode](../../c-runtime-library/reference/setmode.md)   
 [_sopen, _wsopen](../../c-runtime-library/reference/sopen-wsopen.md)