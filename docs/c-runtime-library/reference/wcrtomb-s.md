---
title: "wcrtomb_s | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcrtomb_s
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
f1_keywords: wcrtomb_s
dev_langs: C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb_s function
- multibyte characters
- characters, converting
ms.assetid: 9a8a1bd0-1d60-463d-a3a2-d83525eaf656
caps.latest.revision: "22"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 13134a3e6b34be13d6d878cf94f204bb6c87a458
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="wcrtombs"></a>wcrtomb_s
Преобразует расширенный символ в соответствующее представление многобайтового символа. Версия функции [wcrtomb](../../c-runtime-library/reference/wcrtomb.md) с усовершенствованиями системы безопасности, описанными в разделе [Функции безопасности в CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char *mbchar,  
   size_t sizeOfmbchar,  
   wchar_t *wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
errno_t wcrtomb_s(  
   size_t *pReturnValue,  
   char (&mbchar)[size],  
   wchar_t *wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `pReturnValue`  
 Возвращает записанное число символов или –1 в случае возникновения ошибки.  
  
 [выходной] `mbchar`  
 Итоговый преобразованный многобайтовый символ.  
  
 [in] `sizeOfmbchar`  
 Размер переменной `mbchar` в байтах.  
  
 [in] `wchar`  
 Расширенный символ для преобразования.  
  
 [in] `mbstate`  
 Указатель на объект `mbstate_t` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль в случае успешного выполнения или значение `errno` при возникновении ошибки.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcrtomb_s` преобразует строку расширенных символов, начиная с указанного состояния преобразования, содержащегося в `mbstate`, из значения, содержащегося в `wchar`, в адрес, представленный `mbchar`. Значением `pReturnValue` будет число преобразованных байтов, но не более `MB_CUR_MAX` байтов, или -1, если произошла ошибка.  
  
 Если `mbstate` имеет значение null, используется внутреннее состояние преобразования `mbstate_t`. Если символ, содержащийся в `wchar`, не имеет соответствующий многобайтовый символ, значение `pReturnValue` будет равно -1, и функция возвратит значение `errno` `EILSEQ`.  
  
 Функция `wcrtomb_s` отличается от функции [wctomb_s, _wctomb_s_l](../../c-runtime-library/reference/wctomb-s-wctomb-s-l.md) возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, в приложении необходимо использовать функцию `wcsrlen` вместо функции `wcslen`, если в последующем вызове используется функция `wcsrtombs_s`, а не функция `wcstombs_s.`  
  
 В C++ использование этой функции упрощено наличием шаблонных перегрузок; перегруженные методы могут автоматически определять длину буфера (что исключает необходимость указания аргумента с размером буфера), а также они могут автоматически заменять более старые, незащищенные функции их новыми безопасными аналогами. Дополнительные сведения см. в разделе [Secure Template Overloads](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Исключения  
 Функция `wcrtomb_s` является потокобезопасной, если ни одна из функций в текущем потоке не вызывает `setlocale`, пока выполняется данная функция, и `mbstate` имеет значение null.  
  
## <a name="example"></a>Пример  
  
```  
// crt_wcrtomb_s.c  
// This program converts a wide character  
// to its corresponding multibyte character.  
//  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    errno_t     returnValue;  
    size_t      pReturnValue;  
    mbstate_t   mbstate;  
    size_t      sizeOfmbStr = 1;  
    char        mbchar = 0;  
    wchar_t*    wchar = L"Q\0";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    returnValue = wcrtomb_s(&pReturnValue, &mbchar, sizeof(char),  
                            *wchar, &mbstate);  
    if (returnValue == 0) {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wchar);  
        printf(" was converted to a the \"%c\" ", mbchar);  
        printf("multibyte character.\n");  
    }  
    else  
    {  
        printf("No corresponding multibyte character "  
               "was found.\n");  
    }  
}  
```  
  
```Output  
The corresponding wide character "Q" was converted to a the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcrtomb_s`|\<wchar.h>|  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)