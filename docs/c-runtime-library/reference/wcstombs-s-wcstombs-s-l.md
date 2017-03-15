---
title: "wcstombs_s, _wcstombs_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _wcstombs_s_l
- wcstombs_s
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
- wcstombs_s
- _wcstombs_s_l
dev_langs:
- C++
helpviewer_keywords:
- wcstombs_s function
- string conversion, wide characters
- wide characters, converting
- _wcstombs_s_l function
- wcstombs_s_l function
- characters, converting
- string conversion, multibyte character strings
ms.assetid: 105f2d33-221a-4f6d-864c-23c1865c42af
caps.latest.revision: 31
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 41775d158213a79debbdb4245fc468694df8646e
ms.lasthandoff: 02/24/2017

---
# <a name="wcstombss-wcstombssl"></a>wcstombs_s, _wcstombs_s_l
Преобразует последовательность расширенных символов в соответствующую последовательность многобайтовых символов. Версии функций [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count   
);  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t wcstombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _wcstombs_s_l(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t *wcstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pReturnValue`  
 Количество символов для преобразования.  
  
 [выходной] `mbstr`  
 Адрес буфера для итоговой преобразованной строки многобайтовых символов.  
  
 [in]`sizeInBytes`  
 Размер (в байтах) буфера `mbstr`.  
  
 [in] `wcstr`  
 Указывает на строку расширенных символов, которую необходимо преобразовать.  
  
 [in] `count`  
 Максимальное число байтов для хранения в буфере `mbstr`, не считая завершающий нуль-символ, или [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успеха или код ошибки в случае неудачи.  
  
|Условие ошибки|Возвращаемое значение и `errno`|  
|---------------------|------------------------------|  
|`mbstr` содержит значение `NULL` и `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` равно `NULL`|`EINVAL`|  
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если параметр `count` не имеет значение `_TRUNCATE`; см. примечания ниже).|`ERANGE`|  
  
 Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функция возвращает код ошибки и устанавливает `errno`, как показано в таблице.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcstombs_s` преобразует строку расширенных символов, на которую указывает `wcstr`, в многобайтовые символы, сохраненные в буфере, на который указывает `mbstr`. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.  
  
-   Встретился расширенный нуль-символ.  
  
-   Встретился расширенный символ, который не может быть преобразован.  
  
-   Число байтов, сохраненных в буфере `mbstr`, равно `count`.  
  
 Строка назначения всегда завершается нуль-символом (даже в случае ошибки).  
  
 Если `count` имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), то функция `wcstombs_s` преобразует строки до тех пор, пока буфер назначения не будет заполнен с учетом завершающего нуль-символа.  
  
 Если функция `wcstombs_s` успешно преобразует исходную строку, то размер преобразованной строки в байтах с учетом завершающего нуль-символа будет помещен в параметр `*``pReturnValue` (при условии, что `pReturnValue` не является `NULL`). Это происходит, даже если аргумент `mbstr` имеет значение `NULL`, что позволяет задать необходимый размер буфера. Обратите внимание, что если `mbstr` — `NULL`, `count` игнорируется.  
  
 Если функция `wcstombs_s` обнаруживает расширенный символ, который не удается преобразовать в многобайтовый символ, то помещает в `*``pReturnValue` значение 0, устанавливает пустую строку в качестве целевого буфера, устанавливает `errno` в `EILSEQ` и возвращает `EILSEQ`.  
  
 Если последовательности, на которые указывают параметры `wcstr` и `mbstr`, перекрываются, то поведение `wcstombs_s` не определено.  
  
> [!IMPORTANT]
>  Убедитесь, что строки `wcstr` и `mbstr` не перекрываются, и что параметр `count` правильно отражает количество преобразуемых расширенных символов.  
  
 Функция `wcstombs_s` использует текущий языковой стандарт для любых аспектов поведения, зависящих от языкового стандарта; функция `_wcstombs_s_l` идентична `wcstombs` за исключением того, что она использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcstombs_s`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в статье [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 Эта программа иллюстрирует поведение функции `wcstombs_s`.  
  
```  
// crt_wcstombs_s.c  
// This example converts a wide character  
// string to a multibyte character string.  
#include <stdio.h>  
#include <stdlib.h>  
#include <assert.h>  
  
#define BUFFER_SIZE 100  
  
int main( void )  
{  
    size_t   i;  
    char      *pMBBuffer = (char *)malloc( BUFFER_SIZE );  
    wchar_t*pWCBuffer = L"Hello, world.";  
  
    printf( "Convert wide-character string:\n" );  
  
    // Conversion  
    wcstombs_s(&i, pMBBuffer, (size_t)BUFFER_SIZE,   
               pWCBuffer, (size_t)BUFFER_SIZE );  
  
    // Output  
    printf("   Characters converted: %u\n", i);  
    printf("    Multibyte character: %s\n\n",  
     pMBBuffer );  
  
    // Free multibyte character buffer  
    if (pMBBuffer)  
    {  
    free(pMBBuffer);  
    }  
}  
```  
  
```Output  
Convert wide-character string:  
   Characters converted: 14  
    Multibyte character: Hello, world.  
```  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md)   
 [WideCharToMultiByte](http://msdn.microsoft.com/library/windows/desktop/dd374130)
