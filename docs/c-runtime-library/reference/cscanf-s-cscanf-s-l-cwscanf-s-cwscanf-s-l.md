---
title: "_cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cwscanf_s_l"
  - "_cwscanf_s"
  - "_cscanf_s"
  - "_cscanf_s_l"
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
  - "cscanf_s"
  - "cscanf_s_l"
  - "cwscanf_s"
  - "_cwscanf_s"
  - "_tcscanf_s"
  - "_cscanf_s"
  - "_cwscanf_s_l"
  - "_cscanf_s_l"
  - "cwscanf_s_l"
  - "_tcscanf_s_l"
  - "tcscanf_s"
  - "tcscanf_s_l"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cscanf_s - функция"
  - "_cscanf_s_l - функция"
  - "_cwscanf_s - функция"
  - "_cwscanf_s_l - функция"
  - "_tcscanf_s - функция"
  - "_tcscanf_s_l - функция"
  - "консоль [C++], чтение из"
  - "cscanf_s - функция"
  - "cscanf_s_l - функция"
  - "cwscanf_s - функция"
  - "cwscanf_s_l - функция"
  - "данные [C++], чтение из консоли"
  - "чтение данных [C++], из консоли"
  - "tcscanf_s - функция"
  - "tcscanf_s_l - функция"
ms.assetid: 9ccab74d-916f-42a6-93d8-920525efdf4b
caps.latest.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 24
---
# _cscanf_s, _cscanf_s_l, _cwscanf_s, _cwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает форматированные данные с консоли.  В этих более безопасных версиях [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md) усовершенствована безопасность, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
> [!IMPORTANT]
>  Этот API невозможно использовать в приложениях, запускаемых в среде выполнения Windows.  Дополнительные сведения см. в статье [Функции CRT, которые не поддерживаются с ключом \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Синтаксис  
  
```  
int _cscanf_s(   
   const char *format [,  
   argument] ...   
);  
int _cscanf_s_l(   
   const char *format,  
   locale_t locale [,  
   argument] ...   
);  
int _cwscanf_s(   
   const wchar_t *format [,  
   argument] ...   
);  
int _cwscanf_s_l(   
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
  
 Эти функции проверяют свои параметры.  Если `format` является указателем null, то эти функции вызывают обработчик недопустимого параметра, как описано в [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и `errno`присваивается значение `EINVAL`.  
  
## Заметки  
 Функция `_cscanf_s` считывает данные непосредственно из консоли в места, определяемые `argument`.  Функция [\_getche](../Topic/_getch,%20_getwch.md) используется для чтения символов.  Каждый необязательный параметр в списке должен быть указателем на переменную, которая имеет тип, соответствующий спецификатору типа в `format`.  Аргумент format управляет интерпретацией полей ввода и имеет те же форму и функциональные возможности, что и аргумент `format` функции [scanf\_s](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md).  Обычно `_cscanf_s` выводит вводимый символ, но этого не происходит, если последним вызовом был `_ungetch`.  
  
 Как и другие безопасные версии функций в семействе`scanf` ,`_cscanf_s` и `_cswscanf_s` требуют аргументов размера для символов поля типа `c`, `C`, `s`, `S` и `[`.  Для получения дополнительной информации см. [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md).  
  
> [!NOTE]
>  Параметр размера — типа `unsigned`, а не `size_t`.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_tcscanf_s`|`_cscanf_s`|`_cscanf_s`|`_cwscanf_s`|  
|`_tcscanf_s_l`|`_cscanf_s_l`|`_cscanf_s_l`|`_cwscanf_s_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_cscanf_s`,`_cscanf_s_l`|\<conio.h\>|  
|`_cwscanf_s`, `_cwscanf_s_l`|\<conio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).  
  
## Библиотеки  
 Все версии [библиотек времени выполнения C](../../c-runtime-library/crt-library-features.md).  
  
## Пример  
  
```  
// crt_cscanf_s.c  
// compile with: /c  
/* This program prompts for a string  
 * and uses _cscanf_s to read in the response.  
 * Then _cscanf_s returns the number of items  
 * matched, and the program displays that number.  
 */  
  
#include <stdio.h>  
#include <conio.h>  
  
int main( void )  
{  
   int result, n[3];  
   int i;  
  
   result = _cscanf_s( "%i %i %i", &n[0], &n[1], &n[2] );  
   _cprintf_s( "\r\nYou entered " );  
   for( i=0; i<result; i++ )  
      _cprintf_s( "%i ", n[i] );  
   _cprintf_s( "\r\n" );  
}  
```  
  
## Ввод  
  
```  
1 2 3  
```  
  
## Output  
  
```  
You entered 1 2 3  
```  
  
## См. также  
 [Ввод\-вывод на консоль и порт](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cprintf, \_cprintf\_l, \_cwprintf, \_cwprintf\_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf\_s, \_fscanf\_s\_l, fwscanf\_s, \_fwscanf\_s\_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)   
 [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md)