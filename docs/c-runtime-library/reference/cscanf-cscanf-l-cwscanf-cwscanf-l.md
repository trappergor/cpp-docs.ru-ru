---
title: "_cscanf, _cscanf_l, _cwscanf, _cwscanf_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cscanf_l"
  - "_cscanf"
  - "_cwscanf"
  - "_cwscanf_l"
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
  - "_cwscanf"
  - "cwscanf_l"
  - "tcscanf_l"
  - "_tcscanf_l"
  - "_cscanf"
  - "_cscanf_l"
  - "tcscanf"
  - "cwscanf"
  - "_cwscanf_l"
  - "cscanf_l"
  - "_tcscanf"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cscanf - функция"
  - "_cscanf_l - функция"
  - "_cwscanf - функция"
  - "_cwscanf_l - функция"
  - "_tcscanf - функция"
  - "_tcscanf_l - функция"
  - "cscanf_l - функция"
  - "cwscanf - функция"
  - "cwscanf_l - функция"
  - "данные [C++], чтение из консоли"
  - "чтение данных [C++], из консоли"
  - "tcscanf - функция"
  - "tcscanf_l - функция"
ms.assetid: dbfe7547-b577-4567-a1cb-893fa640e669
caps.latest.revision: 23
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 23
---
# _cscanf, _cscanf_l, _cwscanf, _cwscanf_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает форматированные данные с консоли.  Существуют более безопасные версии этих функций; см. раздел [\_cscanf\_s, \_cscanf\_s\_l, \_cwscanf\_s, \_cwscanf\_s\_l](../../c-runtime-library/reference/cscanf-s-cscanf-s-l-cwscanf-s-cwscanf-s-l.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _cscanf(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_l(   
   const wchar_t *format,  
   locale_t locale [,  
   argument] ...   
);  
```  
  
#### Параметры  
 `format`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные параметры.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Количество полей, которые были успешно преобразованы и присвоены.  Возвращаемое значение не включает поля, которые были считаны, но не были присвоены.  Возвращаемое значение `EOF` при попытке чтения в конце файла.  Это может произойти, если данные, вводимые с клавиатуры, перенаправляются на уровне командной строки операционной системы.  Возвращаемое значение 0 означает, что поля не были присвоены.  
  
## Заметки  
 Функция `_cscanf` считывает данные непосредственно из консоли в места, определяемые `argument`.  Функция [\_getche](../Topic/_getch,%20_getwch.md) используется для чтения символов.  Каждый необязательный параметр в списке должен быть указателем на переменную, которая имеет тип, соответствующий спецификатору типа в `format`.  Аргумент format управляет интерпретацией полей ввода и имеет те же форму и функциональные возможности, что и аргумент `format` функции [scanf](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md).  Обычно `_cscanf` выводит вводимый символ, но этого не происходит, если последним вызовом был `_ungetch`.  
  
 Эта функция проверяет свои параметры.  Если format имеет значение NULL, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, то `errno` устанавливается в `EINVAL`, и функция возвращает `EOF`.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcscanf`|`_cscanf`|`_cscanf`|`_cwscanf`|  
|`_tcscanf_l`|`_cscanf_l`|`_cscanf_l`|`_cwscanf_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_cscanf`,`_cscanf_l`|\<conio.h\>|  
|`_cwscanf`, `_cwscanf_l`|\<conio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Пример  
  
```  
// crt_cscanf.c  
// compile with: /c /W3  
/* This program prompts for a string  
 * and uses _cscanf to read in the response.  
 * Then _cscanf returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int   result, i[3];  
  
   _cprintf_s( "Enter three integers: ");  
   result = _cscanf( "%i %i %i", &i[0], &i[1], &i[2] ); // C4996  
   // Note: _cscanf is deprecated; consider using _cscanf_s instead  
   _cprintf_s( "\r\nYou entered " );  
   while( result-- )  
      _cprintf_s( "%i ", i[result] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## Ввод  
  
```  
1 2 3  
```  
  
## Output  
  
```  
Enter three integers: 1 2 3  
You entered 3 2 1  
```  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, \_fscanf\_l, fwscanf, \_fwscanf\_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf, \_sscanf\_l, swscanf, \_swscanf\_l](../../c-runtime-library/reference/sscanf-sscanf-l-swscanf-swscanf-l.md)