---
title: "_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _fwprintf_p
- _fprintf_p_l
- _fwprintf_p_l
- _fprintf_p
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
apitype: DLLExport
f1_keywords:
- _fprintf_p
- _ftprintf_p
- fwprintf_p
- _fwprintf_p
- fprintf_p
- ftprintf_p
dev_langs: C++
helpviewer_keywords:
- fprintf_p_l function
- fprintf_p function
- _fprintf_p_l function
- _fprintf_p function
- _ftprintf_p_l function
- streams, printing formatted data to
- _fwprintf_p function
- fwprintf_p function
- _ftprintf_p function
- _fwprintf_p_l function
- ftprintf_p function
- printing [C++], formatted data to streams
- ftprintf_p_l function
- fwprintf_p_l function
ms.assetid: 46b082e1-45ba-4383-9ee4-97015aa50bc6
caps.latest.revision: "20"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4eb4bbd2888b0da8fb1c8431cfb7150ed468d86d
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="fprintfp-fprintfpl-fwprintfp-fwprintfpl"></a>_fprintf_p, _fprintf_p_l, _fwprintf_p, _fwprintf_p_l
Выводит форматированные данные в поток.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int _fprintf_p(   
   FILE *stream,  
   const char *format [,  
   argument ]...  
);  
int _fprintf_p_l(   
   FILE *stream,  
   const char *format,  
   locale_t locale [,  
   argument ]...  
);  
int _fwprintf_p(   
   FILE *stream,  
   const wchar_t *format [,  
   argument ]...  
);  
int _fwprintf_p_l(   
   FILE *stream,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ]...  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `stream`  
 Указатель на структуру `FILE`.  
  
 `format`  
 Строка управления форматом.  
  
 `argument`  
 Необязательные аргументы.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Функции `_fprintf_p` и `_fwprintf_p` возвращают число выведенных символов или отрицательное значение в случае ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функция `_fprintf_p` форматирует и выводит набор символов и значений в выходной поток `stream`. Каждый `argument` функции (при наличии) преобразуется и выводится согласно соответствующей спецификации формата в `format`. Для функции `_fprintf_p` аргумент `format` имеет такой же синтаксис и применение, как и для функции `_printf_p`. Эти функции поддерживают позиционные параметры, это означает, что можно изменить порядок параметров, используемых в строке формата. Дополнительные сведения см. в разделе [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md).  
  
 `_fwprintf_p` — версия функции `_fprintf_p` для расширенных символов; в функции `_fwprintf_p` параметр `format` — это строка расширенных символов. Эти функции ведут себя одинаково, если поток открыт в режиме ANSI. Функция `_fprintf_p` на данный момент не поддерживает вывод данных в поток в кодировке Юникод.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта.  
  
> [!IMPORTANT]
>  Убедитесь, что `format` не является строкой, определяемой пользователем.  
  
 Как и небезопасные версии (см. раздел [fprintf, _fprintf_l, fwprintf, _fwprintf_l](../../c-runtime-library/reference/fprintf-fprintf-l-fwprintf-fwprintf-l.md)), эти функции проверяют свои параметры и вызывают обработчик недопустимого параметра, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md), если `stream` или `format` является указателем NULL, либо при наличии неизвестных или неправильно сформированных описателей форматирования. Если продолжение выполнения разрешено, функции возвращают значение -1 и задают для `errno` значение `EINVAL`.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|--------------------------------------|--------------------|-----------------------|  
|`_ftprintf_p`|`_fprintf_p`|`_fprintf_p`|`_fwprintf_p`|  
|`_ftprintf_p_l`|`_fprintf_p_l`|`_fprintf_p_l`|`_fwprintf_p_l`|  
  
 Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md).  
  
## <a name="requirements"></a>Требования  
  
|Функция|Обязательный заголовок|  
|--------------|---------------------|  
|`_fprintf_p`, `_fprintf_p_l`|\<stdio.h>|  
|`_fwprintf_p`, `_fwprintf_p_l`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_fprintf_p.c  
// This program uses _fprintf_p to format various  
// data and print it to the file named FPRINTF_P.OUT. It  
// then displays FPRINTF_P.OUT on the screen using the system  
// function to invoke the operating-system TYPE command.  
//   
  
#include <stdio.h>  
#include <process.h>  
  
int main( void )  
{  
    FILE    *stream = NULL;  
    int     i = 10;  
    double  fp = 1.5;  
    char    s[] = "this is a string";  
    char    c = '\n';  
  
    // Open the file  
    if ( fopen_s( &stream, "fprintf_p.out", "w" ) == 0)  
    {  
        // Format and print data  
        _fprintf_p( stream, "%2$s%1$c", c, s );  
        _fprintf_p( stream, "%d\n", i );  
        _fprintf_p( stream, "%f\n", fp );  
  
        // Close the file  
        fclose( stream );  
    }  
  
    // Verify our data  
    system( "type fprintf_p.out" );  
}  
```  
  
```Output  
this is a string  
10  
1.500000  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [_cprintf, _cprintf_l, _cwprintf, _cwprintf_l](../../c-runtime-library/reference/cprintf-cprintf-l-cwprintf-cwprintf-l.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [_cprintf_p, _cprintf_p_l, _cwprintf_p, _cwprintf_p_l](../../c-runtime-library/reference/cprintf-p-cprintf-p-l-cwprintf-p-cwprintf-p-l.md)   
 [_cprintf_s, _cprintf_s_l, _cwprintf_s, _cwprintf_s_l](../../c-runtime-library/reference/cprintf-s-cprintf-s-l-cwprintf-s-cwprintf-s-l.md)   
 [Позиционные параметры printf_p](../../c-runtime-library/printf-p-positional-parameters.md)   
 [fscanf_s, _fscanf_s_l, fwscanf_s, _fwscanf_s_l](../../c-runtime-library/reference/fscanf-s-fscanf-s-l-fwscanf-s-fwscanf-s-l.md)