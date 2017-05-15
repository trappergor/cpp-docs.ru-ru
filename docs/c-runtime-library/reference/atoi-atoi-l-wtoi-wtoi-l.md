---
title: "atoi, _atoi_l, _wtoi, _wtoi_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wtoi
- _wtoi_l
- atoi
- _atoi_l
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
- api-ms-win-crt-convert-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _tstoi
- _wtoi
- _ttoi
- atoi
- _atoi_l
- _wtoi_l
dev_langs:
- C++
helpviewer_keywords:
- _atoi_l function
- ttoi function
- atoi_l function
- string conversion, to integers
- _wtoi function
- wtoi_l function
- tstoi function
- _ttoi function
- _tstoi function
- _wtoi_l function
- atoi function
- wtoi function
ms.assetid: ad7fda30-28ab-421f-aaad-ef0b8868663a
caps.latest.revision: 22
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
ms.translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: 5ed38a5d4c5a9ff6d976302cc52cc14672a4d60b
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="atoi-atoil-wtoi-wtoil"></a>atoi, _atoi_l, _wtoi, _wtoi_l
Преобразуют строку в целое число.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int atoi(  
   const char *str   
);  
int _wtoi(  
   const wchar_t *str   
);  
int _atoi_l(  
   const char *str,  
   _locale_t locale  
);  
int _wtoi_l(  
   const wchar_t *str,  
   _locale_t locale  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 Строка для преобразования.  
  
 `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая функция возвращает значение `int`, которое создается за счет интерпретации входных символов как числа. Функции `atoi` и `_wtoi` возвращают значение 0, если аргумент невозможно преобразовать в значение этого типа.  
  
 В случае переполнения большими отрицательными целыми значениями возвращается `LONG_MIN`. В подобных условиях `atoi` и `_wtoi` возвращают `INT_MAX` и `INT_MIN`. Во всех случаях, когда диапазон не соблюдается, `errno` принимает значение `ERANGE`. Если переданный параметр имеет значение `NULL`, вызывается обработчик недопустимых параметров, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если продолжение выполнения разрешено, эти функции устанавливают для `errno` значение `EINVAL` и возвращают 0.  
  
## <a name="remarks"></a>Примечания  
 Эти функции преобразуют символьную строку в целое значение (`atoi` и `_wtoi`). Входная строка представляет собой последовательность символов, которые могут обрабатываться как числовое значение указанного типа. Каждая функция прекращает чтение строки на первом знаке, который она не может распознать как часть числа. Этот символ может быть нуль-символом ("\0" или L"\0"), которым завершается строка.  
  
 Аргумент `str` для `atoi` и `_wtoi` принимает следующую форму:  
  
 [`whitespace`] [`sign`] [`digits`]]  
  
 Объект `whitespace` состоит из пробелами или символами табуляции, которые игнорируются. `sign` либо плюс (+) или минус (-); и `digits` — один или несколько цифр.  
  
 Версии этих функций с суффиксом `_l` идентичны, за исключением того, что они используют переданный параметр языкового стандарта вместо текущего языкового стандарта. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_tstoi`|`atoi`|`atoi`|`_wtoi`|  
|`_ttoi`|`atoi`|`atoi`|`_wtoi`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограммы|Обязательный заголовок|  
|--------------|---------------------|  
|`atoi`|\<stdlib.h>|  
|`_atoi_l`, `_wtoi`, `_wtoi_l`|\<stdlib.h> или \<wchar.h>|  
  
## <a name="example"></a>Пример  
 Эта программа показывает, как числа, хранящиеся в виде строки, можно преобразовать в числовые значения с помощью функции `atoi`.  
  
```  
// crt_atoi.c  
// This program shows how numbers   
// stored as strings can be converted to  
// numeric values using the atoi functions.  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <errno.h>  
  
int main( void )  
{  
    char    *str = NULL;  
    int     value = 0;  
  
    // An example of the atoi function.  
    str = "  -2309 ";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function.  
    str = "31412764";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
  
    // Another example of the atoi function   
    // with an overflow condition occuring.  
    str = "3336402735171707160320";  
    value = atoi( str );  
    printf( "Function: atoi( \"%s\" ) = %d\n", str, value );  
    if (errno == ERANGE)  
    {  
       printf("Overflow condition occurred.\n");  
    }  
}  
```  
  
```Output  
Function: atoi( "  -2309 " ) = -2309  
Function: atoi( "31412764" ) = 31412764  
Function: atoi( "3336402735171707160320" ) = 2147483647  
Overflow condition occurred.  
```  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Поддержка чисел с плавающей запятой](../../c-runtime-library/floating-point-support.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [_ecvt](../../c-runtime-library/reference/ecvt.md)   
 [_fcvt](../../c-runtime-library/reference/fcvt.md)   
 [_gcvt](../../c-runtime-library/reference/gcvt.md)   
 [setlocale, _wsetlocale](../../c-runtime-library/reference/setlocale-wsetlocale.md)   
 [_atodbl, _atodbl_l, _atoldbl, _atoldbl_l, _atoflt, _atoflt_l](../../c-runtime-library/reference/atodbl-atodbl-l-atoldbl-atoldbl-l-atoflt-atoflt-l.md)
