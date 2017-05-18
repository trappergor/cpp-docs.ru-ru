---
title: "wcrtomb | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- wcrtomb
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
- wcrtomb
dev_langs:
- C++
helpviewer_keywords:
- wide characters, converting
- wcrtomb function
- multibyte characters
- characters, converting
ms.assetid: 717f1b21-2705-4b7f-b6d0-82adc5224340
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
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: 599802a3038305dd09fafb4b6fb278d05c13afa4
ms.contentlocale: ru-ru
ms.lasthandoff: 03/30/2017

---
# <a name="wcrtomb"></a>wcrtomb
Преобразует расширенный символ в соответствующее представление многобайтового символа. Существует более безопасная версия этой функции; см. раздел [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t wcrtomb(  
   char *mbchar,  
   wchar_t wchar,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcrtomb(  
   char (&mbchar)[size],  
   wchar_t wchar,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `mbchar`  
 Итоговый преобразованный многобайтовый символ.  
  
 [in] `wchar`  
 Расширенный символ для преобразования.  
  
 [in] `mbstate`  
 Указатель на объект `mbstate_t` .  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает число байтов, необходимых для представления преобразованного многобайтового символа, или значение -1, если произошла ошибка.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcrtomb` преобразует строку расширенных символов, начиная с указанного состояния преобразования, содержащегося в `mbstate`, из значения, содержащегося в `wchar`, в адрес, представленный `mbchar`. Возвращаемое значение — число байтов, необходимых для представления в соответствующего многобайтового символа, но не более `MB_CUR_MAX` байт.  
  
 Если `mbstate` имеет значение null, то используется внутренний объект `mbstate_t`, содержащий состояние преобразования `mbchar`. Если у последовательности символов `wchar` нет соответствующего представления в виде многобайтовых символов, возвращается значение -1 и для `errno` устанавливается значение `EILSEQ`.  
  
 Функция `wcrtomb` отличается от функции [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md) возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными. Например, в приложении следует использовать функцию `wcsrlen` вместо функции `wcsnlen`, если в последующем вызове используется функция `wcsrtombs`, а не функция `wcstombs`.  
  
 В C++ эта функция имеет перегрузку шаблона, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Исключения  
 Функция `wcrtomb` является потокобезопасной, если ни одна из функций в текущем потоке не вызывает `setlocale`, пока выполняется данная функция и пока `mbstate` имеет значение null.  
  
## <a name="example"></a>Пример  
  
```  
// crt_wcrtomb.c  
// compile with: /W3  
// This program converts a wide character  
// to its corresponding multibyte character.  
  
#include <string.h>  
#include <stdio.h>  
#include <wchar.h>  
  
int main( void )  
{  
    size_t      sizeOfCovertion = 0;  
    mbstate_t   mbstate;  
    char        mbStr = 0;  
    wchar_t*    wcStr = L"Q";  
  
    // Reset to initial conversion state  
    memset(&mbstate, 0, sizeof(mbstate));  
  
    sizeOfCovertion = wcrtomb(&mbStr, *wcStr, &mbstate); // C4996  
    // Note: wcrtomb is deprecated; consider using wcrtomb_s instead  
    if (sizeOfCovertion > 0)  
    {  
        printf("The corresponding wide character \"");  
        wprintf(L"%s\"", wcStr);  
        printf(" was converted to the \"%c\" ", mbStr);  
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
The corresponding wide character "Q" was converted to the "Q" multibyte character.  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcrtomb`|\<wchar.h>|  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)
