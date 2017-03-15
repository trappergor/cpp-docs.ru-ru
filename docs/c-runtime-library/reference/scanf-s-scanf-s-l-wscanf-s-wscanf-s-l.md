---
title: "scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "wscanf_s"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_scanf_s_l"
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
apitype: "DLLExport"
f1_keywords: 
  - "wscanf_s"
  - "_tscanf_s_l"
  - "_wscanf_s_l"
  - "scanf_s"
  - "_tscanf_s"
  - "_scanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "чтение из входных потоков данных [C++]"
  - "буферы [C++], переполнение буфера"
  - "_scanf_s_l - функция"
  - "_wscanf_s_l - функция"
  - "tscanf_s_l - функция"
  - "tscanf_s - функция"
  - "scanf_s - функция"
  - "чтение из входного потока данных [C++]"
  - "wscanf_s - функция"
  - "_tscanf_s_l - функция"
  - "_tscanf_s - функция"
  - "scanf_s_l - функция"
  - "форматированных данных из входных потоков [C++]"
  - "wscanf_s_l - функция"
  - "буферы [C++], исключение переполнения"
ms.assetid: 42cafcf7-52d6-404a-80e4-b056a7faf2e5
caps.latest.revision: 33
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 33
---
# scanf_s, _scanf_s_l, wscanf_s, _wscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает отформатированные данные из стандартного входного потока. Эти версии [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md) усовершенствованной безопасностью, как описано в [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int scanf_s(  
   const char *format [,  
   argument]...   
);  
int _scanf_s_l(  
   const char *format,  
   locale_t locale [,  
   argument]...   
);  
int wscanf_s(  
   const wchar_t *format [,  
   argument]...   
);  
int _wscanf_s_l(  
   const wchar_t *format,  
   locale_t locale [,  
   argument]...   
);  
```  
  
#### Параметры  
 `format`  
 Строка управления форматированием.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Возвращает количество успешно преобразованных и назначенных полей. Возвращаемое значение не включает поля, которые были прочитаны, но не были назначены. Возвращаемое значение 0 указывает, что поля не были назначены. Значение `EOF` возвращается в случае ошибки или при обнаружении символа конца файла или конца строки при первой попытке чтения символа. Если `format` является `NULL` вызывается указатель, обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функции `scanf_s` и `wscanf_s` возвращают ошибку `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Сведения об этих и других кодах ошибок см. в разделе [errno, \_doserrno, \_sys\_errlist, and \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Функция `scanf_s` считывает данные из стандартного входного потока `stdin` и записывает данные в расположение, указанное параметром `argument`. Каждый параметр `argument` должен быть указателем на переменную, которая имеет тип, соответствующий спецификатору типа в параметре `format`. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
 `wscanf_s` — это версия `scanf_s` с расширенными символами; аргумент `format` для `wscanf_s` — строка расширенных символов.`wscanf_s` и `scanf_s` ведут себя одинаково, если поток открыт в режиме ANSI.`scanf_s` сейчас не поддерживает ввод из потока ЮНИКОДА.  
  
 Версии этих функций с суффиксом `_l` идентичны версиям без суффикса, за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
 В отличие от `scanf` и `wscanf` для `scanf_s` и `wscanf_s` требуется указать размер буфера для всех входных параметров типа `c`, `C`, `s`, `S` или наборы элементов управления строками, заключенные в `[]`. Размер буфера в символах передается как дополнительный параметр, после которого сразу следует указатель на буфер или переменную. Например, при чтении строки размер буфера для этой строки передается следующим образом:  
  
 `char s[10];`  
  
 `scanf_s("%9s", s, (unsigned)_countof(s)); // buffer size is 10, width specification is 9`  
  
 Размер буфера включает завершающее значение NULL. Можно использовать поле спецификации ширины, чтобы гарантировать, что считываемый токен поместится в буфер. Если поле, указывающее ширину, не используется, а данные чтения токена слишком большие и не помещаются в буфер, в этот буфер ничего не записывается.  
  
> [!NOTE]
>  Параметр размера имеет тип `unsigned`, а не `size_t`. Использовать статические приведение для преобразования `size_t` значение `unsigned` для 64\-разрядной конфигурации построения.  
  
 В следующем примере показано, что параметр размера буфера описывает максимальное число символов, а не байтов. В вызове функции `wscanf_s` ширина символов, указанная типом буфера, не соответствует ширине символов, указанной описателем формата.  
  
```  
wchar_t ws[10];  
wscanf_s(L"%9S", ws, (unsigned)_countof(ws));  
```  
  
 Описатель формата `S` показывает использование ширины символов, которая является "противоположной" ширине по умолчанию, поддерживаемой функцией. Ширина символов является однобайтовой, но функция поддерживает двухбайтовые символы. В данном примере демонстрируется считывание строки, состоящей из не более чем 9 однобайтовых символов, и помещение их в буфер двухбайтовых символов. Символы обрабатываются как однобайтовые значения; первые два символа сохраняются в `ws[0]`, вторые два сохраняются в `ws[1]` и т. д.  
  
 В случае символов отдельный символ может быть прочитан следующим образом:  
  
 `char c;`  
  
 `scanf_s("%c", &c, 1);`  
  
 При чтении нескольких символов для строк, которые не завершаются нуль\-символом, целые числа используются как спецификация ширины и размер буфера.  
  
 `char c[4];`  
  
 `scanf_s("%4c", &c, (unsigned)_countof(c)); // not null terminated`  
  
 Для получения дополнительной информации см. [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tscanf_s`|`scanf_s`|`scanf_s`|`wscanf_s`|  
|`_tscanf_s_l`|`_scanf_s_l`|`_scanf_s_l`|`_wscanf_s_l`|  
  
 Для получения дополнительной информации см. [Поля спецификации формата. Функции scanf и wscanf](../Topic/Format%20Specification%20Fields:%20scanf%20and%20wscanf%20Functions.md).  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`scanf_s`, `_scanf_s_l`|\<stdio.h\>|  
|`wscanf_s`, `_wscanf_s_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Консоль не поддерживается в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Стандартные дескрипторы потока, связанные с консолью, `stdin`, `stdout` и `stderr`, необходимо перенаправить, чтобы функции C времени выполнения могли использовать их в приложениях [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)]. Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_scanf_s.c  
// This program uses the scanf_s and wscanf_s functions  
// to read formatted input.  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
   int      i,  
            result;  
   float    fp;  
   char     c,  
            s[80];  
   wchar_t  wc,  
            ws[80];  
  
   result = scanf_s( "%d %f %c %C %s %S", &i, &fp, &c, 1,  
                     &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   printf( "The number of fields input is %d\n", result );  
   printf( "The contents are: %d %f %c %C %s %S\n", i, fp, c,  
           wc, s, ws);  
   result = wscanf_s( L"%d %f %hc %lc %S %ls", &i, &fp, &c, 2,  
                      &wc, 1, s, (unsigned)_countof(s), ws, (unsigned)_countof(ws) );  
   wprintf( L"The number of fields input is %d\n", result );  
   wprintf( L"The contents are: %d %f %C %c %hs %s\n", i, fp,  
            c, wc, s, ws);  
}  
```  
  
 Эта программа создает следующие выходные данные для этих входных данных:  
  
 `71 98.6 h z Byte characters`  
  
 `36 92.3 y n Wide characters`  
  
```Output  
Количество входных поля равен 6, содержимое: 71 z 98.599998 h байт символов полей ввода равно 6, содержимое: 36 92.300003 y n расширенных символов  
```  
  
## Эквивалент в .NET Framework  
  
-   [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
-   [System::Console:: ReadLine](https://msdn.microsoft.com/en-us/library/system.console.readline.aspx)  
  
-   См. также `Parse` методов, таких как [System::double:: Parse](https://msdn.microsoft.com/en-us/library/system.double.parse.aspx).  
  
## См. также  
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Потоковый ввод\-вывод](../../c-runtime-library/stream-i-o.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [sprintf, \_sprintf\_l, swprintf, \_swprintf\_l, \_\_swprintf\_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)