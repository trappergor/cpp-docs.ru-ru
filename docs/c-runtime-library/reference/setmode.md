---
title: "_setmode | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmode"
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
  - "_setmode"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_setmode - функция"
  - "перевод файла [C++], задание режима"
  - "файлы [C++], режимы"
  - "файлы [C++], преобразование"
  - "setmode - функция"
  - "Юникод [C++], вывод консоли"
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _setmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Задает режим преобразования файлов.  
  
## Синтаксис  
  
```  
int _setmode (    int fd,    int mode  );  
```  
  
#### Параметры  
 `fd`  
 Дескриптор файла.  
  
 `mode`  
 Новый режим преобразования.  
  
## Возвращаемое значение  
 При успешном выполнении возвращает предыдущий режим преобразования.  
  
 Если в эту функцию передается недопустимый параметр, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эта функция возвращает значение \-1 и задает для `errno` значение `EBADF`, которое указывает на недопустимый дескриптор файла, или `EINVAL`, которое указывает на недопустимый аргумент `mode`.  
  
 Дополнительные сведения об этих и других кодах возврата см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `_setmode` задает в качестве параметра `mode` режим преобразования файла, заданный `fd`.  При передаче `_O_TEXT` как параметра `mode` задается текстовый \(преобразованный\) режим.  Комбинация символов возврата каретки и перевода строки \(CR\-LF\) преобразуется в один символ перевода строки в выводе.  Символы перевода строки преобразуются в комбинацию CR\-LF в выводе.  Передача `_O_BINARY` задает двоичный режим \(без преобразования\), в котором такие преобразования подавляются.  
  
 Можно также передать флаги `_O_U16TEXT`, `_O_U8TEXT` или \_`O_WTEXT`, чтобы включить режим Юникода, как демонстрируется во втором примере ниже в этом документе.  `_setmode`, как правило, используется для изменения режима преобразования `stdin` и `stdout` по умолчанию, однако ее можно использовать для любого файла.  Если вы применяете функцию `_setmode` к дескриптору файла для потока, ее необходимо вызывать до выполнения любых операций ввода или вывода в потоке.  
  
> [!CAUTION]
>  Если выполняется запись данных в файловый поток, необходимо явно сбросить код, используя [fflush](../Topic/fflush.md) перед использованием функции `_setmode` для изменения режима.  Если не выполнить сброс кода, может возникнуть непредвиденное поведение.  Если данные не записывались в поток, выполнять сброс кода не нужно.  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|Необязательные заголовки|  
|------------------|----------------------------|------------------------------|  
|`_setmode`|\<io.h\>|\<fcntl.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
  **"stdin" успешно переведен в двоичный режим**   
## Пример  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
  
```  
  
## Эквивалент .NET Framework  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="fe03c471a7a38d5378cea62467482dae" class\="tgtSentence"\>System::IO::BinaryReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="105e62b7505c25e3e182779c87f145eb" class\="tgtSentence"\>System::IO::TextReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)  
  
## См. также  
 [Обработка файлов](../../c-runtime-library/file-handling.md)   
 [Функция \_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)