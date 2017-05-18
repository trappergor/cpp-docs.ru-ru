---
title: "sscanf, _sscanf_l, swscanf, _swscanf_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- swscanf
- sscanf
- _sscanf_l
- _swscanf_l
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
- _sscanf_l
- _stscanf
- swscanf
- _stscanf_l
- sscanf
- _swscanf_l
dev_langs:
- C++
helpviewer_keywords:
- swscanf function
- _stscanf function
- sscanf function
- _stscanf_l function
- _sscanf_l function
- _swscanf_l function
- swscanf_l function
- strings [C++], reading data from
- stscanf function
- reading data, strings
- strings [C++], reading
- sscanf_l function
- stscanf_l function
ms.assetid: c2dcf0d2-9798-499f-a4a8-06f7e2b9a80c
caps.latest.revision: 26
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
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: b124ba5aa0fef8efd6d44b405fbc608709e05d72
ms.contentlocale: ru-ru
ms.lasthandoff: 04/04/2017

---
# <a name="sscanf-sscanfl-swscanf-swscanfl"></a>sscanf, _sscanf_l, swscanf, _swscanf_l
Считывают форматированные данные из строки. Существуют более безопасные версии этих функций; см. раздел [sscanf_s, _sscanf_s_l, swscanf_s, _swscanf_s_l](../../c-runtime-library/reference/sscanf-s-sscanf-s-l-swscanf-s-swscanf-s-l.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
int sscanf(  
   const char *buffer,  
   const char *format [,  
   argument ] ...   
);  
int _sscanf_l(  
   const char *buffer,  
   const char *format,  
   locale_t locale [,  
   argument ] ...   
);  
int swscanf(  
   const wchar_t *buffer,  
   const wchar_t *format [,  
   argument ] ...   
);  
int _swscanf_l(  
   const wchar_t *buffer,  
   const wchar_t *format,  
   locale_t locale [,  
   argument ] ...   
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `buffer`  
 Сохраненные данные  
  
 `format`  
 Строка управления форматом. Дополнительные сведения см. в разделе [Спецификации формата](../../c-runtime-library/format-specification-fields-scanf-and-wscanf-functions.md).  
  
 `argument`  
 Необязательные аргументы  
  
 `locale`  
 Используемый языковой стандарт  
  
## <a name="return-value"></a>Возвращаемое значение  
 Каждая из этих функций возвращает количество полей, которые были успешно преобразованы и присвоены; возвращаемое значение не включает поля, которые были считаны, но не были присвоены. Возвращаемое значение 0 указывает, что поля не были назначены. Если до первого преобразования возникает ошибка или достигается конец строки, возвращается значение `EOF`.  
  
 Если `buffer` или `format` является указателем `NULL`, вызывается обработчик недопустимых параметров, как описано в статье [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если разрешается продолжать выполнение, эти функции возвращают -1 и задают `errno` значение `EINVAL`.  
  
 Дополнительные сведения об этих и других кодах ошибок см. в разделе [_doserrno, errno, _sys_errlist и _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Примечания  
 Функция `sscanf` считывает данные из `buffer` в расположение, заданное параметрами `argument`. Каждый параметр `argument` должен быть указателем на переменную, которая имеет тип, соответствующий спецификатору типа в параметре `format`. Аргумент `format` определяет интерпретацию полей входных данных и имеет такую же форму и функцию, как аргумент `format` для функции `scanf`. Если копирование производится между перекрывающимися строками, поведение не определено.  
  
> [!IMPORTANT]
>  При использовании `sscanf` для чтения строки всегда следует указывать ширину для формата `%s` (например, `"%32s"` вместо `"%s"`); в противном случае ввод в неправильном формате может легко привести к переполнению буфера.  
  
 `swscanf` — это двухбайтовая версия `sscanf`; аргументы для `swscanf` представляют собой двухбайтовые строки. `sscanf` не обрабатывает многобайтовые шестнадцатеричные символы. `swscanf` не обрабатывает шестнадцатеричные символы Юникода полной ширины и символы "зоны совместимости". В противном случае поведение `swscanf` и `sscanf` идентично.  
  
 Версии этих функций с суффиксом `_l` идентичны за исключением того, что они используют переданный параметр языкового стандарта вместо языкового стандарта текущего потока.  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|`_stscanf`|`sscanf`|`sscanf`|`swscanf`|  
|`_stscanf_l`|`_sscanf_l`|`_sscanf_l`|`_swscanf_l`|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`sscanf`, `_sscanf_l`|\<stdio.h>|  
|`swscanf`, `_swscanf_l`|\<stdio.h> или \<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
  
```  
// crt_sscanf.c  
// compile with: /W3  
// This program uses sscanf to read data items  
// from a string named tokenstring, then displays them.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char  tokenstring[] = "15 12 14...";  
   char  s[81];  
   char  c;  
   int   i;  
   float fp;  
  
   // Input various data from tokenstring:  
   // max 80 character string:  
   sscanf( tokenstring, "%80s", s ); // C4996  
   sscanf( tokenstring, "%c", &c );  // C4996  
   sscanf( tokenstring, "%d", &i );  // C4996  
   sscanf( tokenstring, "%f", &fp ); // C4996  
   // Note: sscanf is deprecated; consider using sscanf_s instead  
  
   // Output the data read  
   printf( "String    = %s\n", s );  
   printf( "Character = %c\n", c );  
   printf( "Integer:  = %d\n", i );  
   printf( "Real:     = %f\n", fp );  
}  
```  
  
```Output  
String    = 15  
Character = 1  
Integer:  = 15  
Real:     = 15.000000  
```  
  
## <a name="see-also"></a>См. также  
 [Потоковый ввод-вывод](../../c-runtime-library/stream-i-o.md)   
 [fscanf, _fscanf_l, fwscanf, _fwscanf_l](../../c-runtime-library/reference/fscanf-fscanf-l-fwscanf-fwscanf-l.md)   
 [scanf, _scanf_l, wscanf, _wscanf_l](../../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [sprintf, _sprintf_l, swprintf, _swprintf_l, \__swprintf_l](../../c-runtime-library/reference/sprintf-sprintf-l-swprintf-swprintf-l-swprintf-l.md)   
 [snprintf, _snprintf, _snprintf_l, _snwprintf, _snwprintf_l](../../c-runtime-library/reference/snprintf-snprintf-snprintf-l-snwprintf-snwprintf-l.md)
