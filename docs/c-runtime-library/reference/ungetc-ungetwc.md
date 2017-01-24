---
title: "ungetc, ungetwc | Microsoft Docs"
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
  - "ungetwc"
  - "ungetc"
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
  - "_ungettc"
  - "ungetwc"
  - "ungetc"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ungettc - функция"
  - "знаки, возвращение в поток"
  - "ungetc - функция"
  - "ungettc - функция"
  - "ungetwc - функция"
ms.assetid: e0754f3a-b4c6-408f-90c7-e6387b830d84
caps.latest.revision: 16
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ungetc, ungetwc
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Отправляет символ обратно в поток.  
  
## Синтаксис  
  
```  
int ungetc(  
   int c,  
   FILE *stream   
);  
wint_t ungetwc(  
   wint_t c,  
   FILE *stream   
);  
```  
  
#### Параметры  
 `c`  
 Символ, который требуется вернуть.  
  
 `stream`  
 Указатель на структуру `FILE`.  
  
## Возвращаемое значение  
 В случае успеха каждая из этих функций возвращает символьный аргумент `c`*.* Если `c` нельзя отправить обратно или если не было прочитано символов, входной поток не изменяется и `ungetc` возвращает `EOF`; `ungetwc` возвращает `WEOF`.  Если параметр `stream` имеет значение `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если выполнение может быть продолжено, возвращается `EOF` или `WEOF`, и `errno` принимает значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `ungetc` помещает символ `c` обратно в `stream` и удаляет индикатор конца файла.  Поток должен быть открыт для чтения.  Последующая операция чтения из `stream` начинается с `c`*.* Попытка отправить `EOF` в поток с помощью `ungetc` игнорируется.  
  
 Символы, помещенные в поток функцией `ungetc`, могут быть стерты, если `fflush`, `fseek`, `fsetpos` или `rewind` вызывается до того, как символ прочитан из потока.  Индикатор позиции файла будет иметь значение, которое он имел до того, как символы были отправлены обратно.  Внешнее хранилище, соответствующее потоку, остается неизменным.  При успешном вызове `ungetc` для текстового потока, индикатор позиции файла остается не заданным, пока отправленные в конец символы не прочитаны или не отброшены.  При каждом успешном вызове `ungetc` для двоичного потока, индикатор позиции файла уменьшается; если его значение равно 0, то это значение не определено после вызова.  
  
 Результаты непредсказуемы, если `ungetc` вызывается дважды без операции чтения или позиционирования файла между двумя вызовами.  После вызова `fscanf`, вызов `ungetc` может завершиться неудачей, если не будет выполнена другая операция чтения \(например, `getc`\).  Это происходит потому, что `fscanf` сам вызывает `ungetc`.  
  
 `ungetwc` — это версия `ungetc` для расширенных символов.  Однако при каждом успешном вызове `ungetwc` для текстового или двоичного потока, значение индикатора позиции файла не указано до тех пор, пока все отправленные в конец символы не считаны или отброшены.  
  
 Эти функции потокобезопасны и блокируют чувствительные данные во время выполнения.  Для неблокирующей версии см. [\_ungetc\_nolock, \_ungetwc\_nolock](../Topic/_ungetc_nolock,%20_ungetwc_nolock.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE & \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_ungettc`|`ungetc`|`ungetc`|`ungetwc`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`ungetc`|\<stdio.h\>|  
|`ungetwc`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Стандартные дескрипторы потока, связанные с консолью — `stdin`, `stdout` и `stderr` — необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)].  Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_ungetc.c  
// This program first converts a character  
// representation of an unsigned integer to an integer. If  
// the program encounters a character that is not a digit,  
// the program uses ungetc to replace it in the  stream.  
//  
  
#include <stdio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
   int result = 0;  
  
   // Read in and convert number:  
   while( ((ch = getchar()) != EOF) && isdigit( ch ) )  
      result = result * 10 + ch - '0';    // Use digit.  
   if( ch != EOF )  
      ungetc( ch, stdin );                // Put nondigit back.  
   printf( "Number = %d\nNext character in stream = '%c'",   
            result, getchar() );  
}  
```  
  
  **`521a`Number \= 521**  
**Next character in stream \= 'a'**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [putc, putwc](../../c-runtime-library/reference/putc-putwc.md)