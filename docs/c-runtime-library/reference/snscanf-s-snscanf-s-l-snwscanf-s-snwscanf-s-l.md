---
title: "_snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_snwscanf_s_l"
  - "_snwscanf_s"
  - "_snscanf_s"
  - "_snscanf_s_l"
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
  - "_sntscanf_s"
  - "snscanf_s"
  - "_snwscanf_s_l"
  - "sntscanf_s_l"
  - "snwscanf_s_l"
  - "snwscanf_s"
  - "_snscanf_s"
  - "_snwscanf_s"
  - "snscanf_s_l"
  - "_sntscanf_s_l"
  - "_snscanf_s_l"
  - "sntscanf_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_snscanf_s - функция"
  - "_snscanf_s_l - функция"
  - "_sntscanf_s - функция"
  - "_sntscanf_s_l - функция"
  - "_snwscanf_s - функция"
  - "_snwscanf_s_l - функция"
  - "чтение данных, строки"
  - "snscanf_s - функция"
  - "snscanf_s_l - функция"
  - "sntscanf_s - функция"
  - "sntscanf_s_l - функция"
  - "snwscanf_s - функция"
  - "snwscanf_s_l - функция"
  - "строки [C++], чтение"
  - "строки [C++], чтение данных из"
ms.assetid: 72356653-7362-461a-af73-597b9c0a8094
caps.latest.revision: 24
caps.handback.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _snscanf_s, _snscanf_s_l, _snwscanf_s, _snwscanf_s_l
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Считывает форматированные данные указанной длины из строки.  Здесь представлены версии [\_snscanf, \_snscanf\_l, \_snwscanf, \_snwscanf\_l](../../c-runtime-library/reference/snscanf-snscanf-l-snwscanf-snwscanf-l.md) с усовершенствованной безопасностью, как описано в разделе [Функции безопасности в CRT](../Topic/Security%20Features%20in%20the%20CRT.md).  
  
## Синтаксис  
  
```  
int __cdecl _snscanf_s(  
   const char * input,  
   size_t length,  
   const char * format,  
   ...  
);  
int __cdecl _snscanf_s_l(  
   const char * input,  
   size_t length,  
   const char * format,  
   locale_t locale,  
   ...  
);  
int __cdecl _snwscanf_s(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   ...  
);  
int __cdecl _snwscanf_s_l(  
   const wchar_t * input,  
   size_t length,  
   const wchar_t * format,  
   locale_t locale,  
   …  
);  
```  
  
#### Параметры  
 `input`  
 Входная строка для анализа.  
  
 `length`  
 Количество символов для анализа в `input`.  
  
 `format`  
 Один или несколько описателей формата.  
  
 `... (optional)`  
 Переменные, которые будут использоваться для хранения извлеченных из входной строки значений с помощью описателей формата в `format`.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые успешно преобразуются и присваиваются; возвращаемое значение не включает поля, которые были считаны, но не присвоены.  Возвращаемое значение 0 указывает, что поля не были присвоены.  Возвращаемое значение равно `EOF` в случае ошибки или если конец строки достигнут до первого преобразования.  Для получения дополнительной информации см. [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md).  
  
 Если параметр `input` или `format` указывает на `NULL`, вызывается обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md).  Если продолжение выполнения разрешено, эти функции возвращают `EOF` и устанавливают для `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [\_doserrno, errno, \_sys\_errlist и \_sys\_nerr](../Topic/errno,%20_doserrno,%20_sys_errlist,%20and%20_sys_nerr.md).  
  
## Заметки  
 Эта функция аналогична `sscanf_s` за исключением того, что она обеспечивает возможность задать фиксированное число символов входной строки для анализа.  Для получения дополнительной информации см. [sscanf\_s, \_sscanf\_s\_l, swscanf\_s, \_swscanf\_s\_l](../Topic/sscanf_s,%20_sscanf_s_l,%20swscanf_s,%20_swscanf_s_l.md).  
  
 Параметр размера буфера необходимо указывать с символами поля типа `c`, `C`, `s`, `S` и `[`.  Для получения дополнительной информации см. [Символы поля типа scanf](../../c-runtime-library/scanf-type-field-characters.md).  
  
> [!NOTE]
>  Параметр размера — типа `unsigned`, а не `size_t`.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|\_UNICODE и \_MBCS не определены|\_MBCS определено|\_UNICODE определено|  
|--------------------------|--------------------------------------|-----------------------|--------------------------|  
|`_sntscanf_s`|`_snscanf_s`|`_snscanf_s`|`_snwscanf_s`|  
|`_sntscanf_s_l`|`_snscanf_s_l`|`_snscanf_s_l`|`_snwscanf_s_l`|  
  
## Требования  
  
|Подпрограмма|Обязательный заголовок|  
|------------------|----------------------------|  
|`_snscanf_s`, \_`snscanf_s_l`|\<stdio.h\>|  
|`_snwscanf_s`, `_snwscanf_s_l`|\<stdio.h\> или \<wchar.h\>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## Пример  
  
```  
// crt_snscanf_s.c  
// This example scans a string of   
// numbers, using both the character  
// and wide character secure versions  
// of the snscanf function.  
  
#include <stdio.h>  
  
int main( )  
{  
    char        str1[] = "15 12 14...";  
    wchar_t     str2[] = L"15 12 14...";  
    char        s1[3];  
    wchar_t     s2[3];  
    int         i;  
    float       fp;  
  
    i = _snscanf_s( str1, 6,  "%s %f", s1, 3, &fp);  
    printf_s("_snscanf_s converted %d fields: ", i);  
    printf_s("%s and %f\n", s1, fp);  
  
    i = _snwscanf_s( str2, 6,  L"%s %f", s2, 3, &fp);  
    wprintf_s(L"_snwscanf_s converted %d fields: ", i);  
    wprintf_s(L"%s and %f\n", s2, fp);  
}  
```  
  
  **\_snscanf\_s converted 2 fields: 15 and 12.000000**  
**\_snwscanf\_s converted 2 fields: 15 and 12.000000**   
## Эквивалент в .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызовов неуправляемого кода](../Topic/Platform%20Invoke%20Examples.md).  
  
## См. также  
 [Спецификация ширины scanf](../../c-runtime-library/scanf-width-specification.md)