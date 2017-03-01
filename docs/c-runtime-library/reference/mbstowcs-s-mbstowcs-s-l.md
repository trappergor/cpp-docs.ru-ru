---
title: "mbstowcs_s, _mbstowcs_s_l | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _mbstowcs_s_l
- mbstowcs_s
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
- _mbstowcs_s_l
- mbstowcs_s
dev_langs:
- C++
helpviewer_keywords:
- _mbstowcs_s_l function
- mbstowcs_s function
- mbstowcs_s_l function
ms.assetid: 2fbda953-6918-498f-b440-3e7b21ed65a4
caps.latest.revision: 31
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 3a5c84be1336d762289705102c1f2213f04642ea
ms.lasthandoff: 02/24/2017

---
# <a name="mbstowcss-mbstowcssl"></a>mbstowcs_s, _mbstowcs_s_l
Преобразует последовательность многобайтовых символов в соответствующую последовательность расширенных символов. Это версии функции [mbstowcs, _mbstowcs_l](../../c-runtime-library/reference/mbstowcs-mbstowcs-l.md) с усовершенствованной безопасностью, как описано в разделе [Усовершенствования безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count   
);  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t *wcstr,  
   size_t sizeInWords,  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
);  
template <size_t size>  
errno_t mbstowcs_s(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count   
); // C++ only  
template <size_t size>  
errno_t _mbstowcs_s_l(  
   size_t *pReturnValue,  
   wchar_t (&wcstr)[size],  
   const char *mbstr,  
   size_t count,  
   _locale_t locale  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pReturnValue`  
 Количество символов для преобразования.  
  
 [выходной] `wcstr`  
 Адрес буфера для результирующей преобразованной строки расширенных символов.  
  
 [in] `sizeInWords`  
 Размер буфера `wcstr` в словах.  
  
 [in]`mbstr`  
 Адрес последовательности многобайтовых символов, заканчивающейся нуль-символом.  
  
 [in] `count`  
 Максимальное число расширенных символов для хранения в буфере `wcstr`, не считая завершающий нуль-символ, или [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `locale`  
 Используемый языковой стандарт.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успеха или код ошибки в случае неудачи.  
  
|Условие ошибки|Возвращаемое значение и `errno`|  
|---------------------|------------------------------|  
|`wcstr` содержит значение `NULL` и `sizeInWords` > 0|`EINVAL`|  
|`mbstr` равно `NULL`|`EINVAL`|  
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если параметр `count` не имеет значение `_TRUNCATE`; см. примечания ниже).|`ERANGE`|  
|`wcstr` не имеет значение `NULL` и `sizeInWords` == 0|`EINVAL`|  
  
 Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функция возвращает код ошибки и устанавливает `errno`, как показано в таблице.  
  
## <a name="remarks"></a>Примечания  
 Функция `mbstowcs_s` преобразует строку многобайтовых символов, на которую указывает `mbstr`, в расширенные символы, сохраненные в буфере, на который указывает `wcstr`. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.  
  
-   Встретился многобайтовый символ null.  
  
-   Встретился недопустимый многобайтовый символ.  
  
-   Число расширенных символов, сохраненных в буфере `wcstr`, равно `count`.  
  
 Строка назначения всегда завершается нуль-символом (даже в случае ошибки).  
  
 Если `count` имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), то функция `mbstowcs_s` преобразует строки до тех пор, пока буфер назначения не будет заполнен с учетом завершающего нуль-символа.  
  
 Если функция `mbstowcs_s` успешно преобразует исходную строку, то размер преобразованной строки в расширенных символах с учетом завершающего нуль-символа будет помещен в параметр `*``pReturnValue` (при условии, что `pReturnValue` не является указателем `NULL`). Это происходит, даже если аргумент `wcstr` имеет значение `NULL`, что позволяет задать необходимый размер буфера. Обратите внимание, что если `wcstr` имеет значение `NULL`, `count` игнорируется и `sizeInWords` должно быть равно 0.  
  
 Если функция `mbstowcs_s` обнаруживает недопустимый многобайтовый символ, то помещает в `*``pReturnValue` значение 0, устанавливает пустую строку в качестве целевого буфера, присваивает `errno` значение `EILSEQ` и возвращает `EILSEQ`.  
  
 Если последовательности, на которые указывают параметры `mbstr` и `wcstr`, перекрываются, то поведение `mbstowcs_s` не определено.  
  
> [!IMPORTANT]
>  Убедитесь, что строки `wcstr` и `mbstr` не перекрываются, и что параметр `count` правильно отражает количество преобразуемых многобайтовых символов.  
  
 Функция `mbstowcs_s` использует текущий языковой стандарт для любых аспектов поведения, зависящих от языкового стандарта; функция `_mbstowcs_s_l` идентична за исключением того, что она использует переданный языковой стандарт. Дополнительные сведения см. в разделе [Языковой стандарт](../../c-runtime-library/locale.md).  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`mbstowcs_s`|\<stdlib.h>|  
|`_mbstowcs_s_l`|\<stdlib.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="net-framework-equivalent"></a>Эквивалент .NET Framework  
 Неприменимо. Для вызова стандартной функции C используйте `PInvoke`. Дополнительные сведения см. в разделе [Примеры вызова неуправляемого кода](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [MultiByteToWideChar](http://msdn.microsoft.com/library/windows/desktop/dd319072)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md)   
 [mbtowc, _mbtowc_l](../../c-runtime-library/reference/mbtowc-mbtowc-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)
