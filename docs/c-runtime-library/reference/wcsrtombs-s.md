---
title: "wcsrtombs_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs_s
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
f1_keywords: wcsrtombs_s
dev_langs: C++
helpviewer_keywords:
- string conversion, wide characters
- wcsrtombs_s function
- wide characters, strings
ms.assetid: 9dccb766-113c-44bb-9b04-07a634dddec8
caps.latest.revision: "27"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 025acdf18d0e5322ef43de800e3577233a93cb86
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wcsrtombss"></a>wcsrtombs_s
Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Версия функции [wcsrtombs](../../c-runtime-library/reference/wcsrtombs.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char *mbstr,  
   size_t sizeInBytes,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcsrtombs_s(  
   size_t *pReturnValue,  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pReturnValue`  
 Количество символов для преобразования.  
  
 [выходной] `mbstr`  
 Адрес буфера для итоговой преобразованной строки многобайтовых символов.  
  
 [выходной] `sizeInBytes`  
 Размер (в байтах) буфера `mbstr`.  
  
 [in] `wcstr`  
 Указывает на строку расширенных символов, которую необходимо преобразовать.  
  
 [in] `count`  
 Максимальное число байтов для сохранения в буфере `mbstr` или [_TRUNCATE](../../c-runtime-library/truncate.md).  
  
 [in] `mbstate`  
 Указатель на объект состояния преобразования `mbstate_t`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Нуль в случае успеха или код ошибки в случае неудачи.  
  
|Условие ошибки|Возвращаемое значение и `errno`|  
|---------------------|------------------------------|  
|`mbstr` содержит значение `NULL` и `sizeInBytes` > 0|`EINVAL`|  
|`wcstr` равно `NULL`|`EINVAL`|  
|Буфер назначения слишком мал, чтобы вместить преобразованную строку (если параметр `count` не имеет значение `_TRUNCATE`; см. примечания ниже).|`ERANGE`|  
  
 Если выполняется какое-либо из этих условий, вызывается исключение о недопустимом параметре, как описано в разделе [Проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, то функция возвращает код ошибки и устанавливает `errno`, как показано в таблице.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcsrtombs_s` преобразует строку расширенных символов, на которую указывает `wcstr`, в многобайтовые символы, сохраненные в буфере, на который указывает `mbstr`. При этом используется состояние преобразования, содержащееся в `mbstate`. Преобразование будет продолжаться для каждого символа до тех пор, пока не будет выполнено одно из указанных ниже условий.  
  
-   Встретился расширенный нуль-символ.  
  
-   Встретился расширенный символ, который не может быть преобразован.  
  
-   Число байтов, сохраненных в буфере `mbstr`, равно `count`.  
  
 Строка назначения всегда завершается нуль-символом (даже в случае ошибки).  
  
 Если `count` имеет специальное значение [_TRUNCATE](../../c-runtime-library/truncate.md), то функция `wcsrtombs_s` преобразует строки до тех пор, пока буфер назначения не будет заполнен с учетом завершающего нуль-символа.  
  
 Если функция `wcsrtombs_s` успешно преобразует исходную строку, то размер преобразованной строки в байтах с учетом завершающего нуль-символа будет помещен в параметр `*pReturnValue` (при условии, что `pReturnValue` не является `NULL`). Это происходит, даже если аргумент `mbstr` имеет значение `NULL`, что позволяет задать необходимый размер буфера. Обратите внимание, что если `mbstr` — `NULL`, `count` игнорируется.  
  
 Если функция `wcsrtombs_s` обнаруживает расширенный символ, который не удается преобразовать в многобайтовый символ, то помещает в `*pReturnValue` значение -1, устанавливает пустую строку в качестве целевого буфера, устанавливает `errno``EILSEQ` и возвращает `EILSEQ`.  
  
 Если последовательности, на которые указывают параметры `wcstr` и `mbstr`, перекрываются, то поведение `wcsrtombs_s` не определено. На функцию `wcsrtombs_s` влияет категория LC_TYPE текущего языкового стандарта.  
  
> [!IMPORTANT]
>  Убедитесь, что строки `wcstr` и `mbstr` не перекрываются и что параметр `count` правильно отражает количество преобразуемых расширенных символов.  
  
 Функция `wcsrtombs_s` отличается от функции [wcstombs_s, _wcstombs_s_l](../../c-runtime-library/reference/wcstombs-s-wcstombs-s-l.md) возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, в приложении необходимо использовать функцию `wcsrlen` вместо функции `wcslen`, если в последующем вызове используется функция `wcsrtombs_s`, а не функция `wcstombs_s.`  
  
 В C++ использование данных функций упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Исключения  
 Функция `wcsrtombs_s` является потокобезопасной, если ни одна из функций в текущем потоке не вызывает `setlocale`, пока выполняется данная функция, и `mbstate` имеет значение null.  
  
## <a name="example"></a>Пример  
  
```  
// crt_wcsrtombs_s.cpp  
//   
// This code example converts a wide  
// character string into a multibyte  
// character string.  
//  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
void main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    errno_t         err;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    err = wcsrtombs_s(&countConverted, mbString, MB_BUFFER_SIZE,  
                      &wcsIndirectString, MB_BUFFER_SIZE, &mbstate);  
    if (err == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfully converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfully converted.  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcsrtombs_s`|\<wchar.h>|  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)