---
title: "wcsrtombs | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: wcsrtombs
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
f1_keywords: wcsrtombs
dev_langs: C++
helpviewer_keywords:
- wcsrtombs function
- string conversion, wide characters
- wide characters, strings
ms.assetid: a8d21fec-0d36-4085-9d81-9b1c61c7259d
caps.latest.revision: "26"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 71924eb149097c90fbfe2f3ceb2981ea45e97995
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="wcsrtombs"></a>wcsrtombs
Преобразует строку расширенных символов в соответствующее представление многобайтовой строки. Существует более безопасная версия этой функции; см. раздел [wcsrtombs_s](../../c-runtime-library/reference/wcsrtombs-s.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t wcsrtombs(  
   char *mbstr,  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
);  
template <size_t size>  
size_t wcsrtombs(  
   char (&mbstr)[size],  
   const wchar_t **wcstr,  
   sizeof count,  
   mbstate_t *mbstate  
); // C++ only  
```  
  
#### <a name="parameters"></a>Параметры  
 [выходной] `mbstr`  
 Расположение адреса итоговой преобразованной строки многобайтовых символов.  
  
 [in] `wcstr`  
 Косвенно указывает на расположение преобразуемой строки расширенных символов.  
  
 [in] `count`  
 Количество символов для преобразования.  
  
 [in] `mbstate`  
 Указатель на объект состояния преобразования `mbstate_t`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Возвращает число успешно преобразованных байтов, не включая завершающий байт NULL (если имеется); в противном случае — значение -1, если произошла ошибка.  
  
## <a name="remarks"></a>Примечания  
 Функция `wcsrtombs` преобразует строку расширенных символов, начиная с указанного состояния преобразования, содержащегося в `mbstate`, из значений, косвенно указанных в `wcstr`, в адрес `mbstr`. Преобразование будет продолжаться для каждого символа до тех пор, пока не встретится расширенный завершающий символ null, или не обнаружится несоответствующий символ, или когда следующий символ может превысить ограничение, указанное в `count`. Если функция `wcsrtombs` встречает расширенный нуль-символ (L"\0") перед или после `count` символов, она преобразовывает его в 8-битный 0 и останавливается.  
  
 Таким образом, строка многобайтовых символов `mbstr` завершается символом NULL только в том случае, если функция `wcsrtombs` встречает расширенный нуль-символ во время преобразования. Если последовательности, на которые указывают параметры `wcstr` и `mbstr`, перекрываются, то поведение `wcsrtombs` не определено. На функцию `wcsrtombs` влияет категория LC_TYPE текущего языкового стандарта.  
  
 Функция `wcsrtombs` отличается от функции [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md) возможностью перезапуска. Состояние преобразования хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, в приложении следует использовать функцию `wcsrlen` вместо функции `wcsnlen`, если в последующем вызове используется функция `wcsrtombs`, а не функция `wcstombs`.  
  
 Если аргумент `mbstr` равен `NULL`, функция `wcsrtombs` возвращает необходимый размер строки назначения в байтах. Если `mbstate` имеет значение null, используется внутреннее состояние преобразования `mbstate_t`. Если у последовательности символов `wchar` нет соответствующего представления в виде многобайтовых символов, возвращается значение -1 и для `errno` устанавливается значение `EILSEQ`.  
  
 В C++ эта функция имеет шаблонную перегрузку, которая вызывает более новые и безопасные аналоги этой функции. Дополнительные сведения см. в разделе [Безопасные перегрузки шаблонов](../../c-runtime-library/secure-template-overloads.md).  
  
## <a name="exceptions"></a>Исключения  
 Функция `wcsrtombs` является потокобезопасной, если ни одна из функций в текущем потоке не вызывает `setlocale`, пока выполняется данная функция, и `mbstate` не имеет значение null.  
  
## <a name="example"></a>Пример  
  
```  
// crt_wcsrtombs.cpp  
// compile with: /W3  
// This code example converts a wide  
// character string into a multibyte  
// character string.  
  
#include <stdio.h>  
#include <memory.h>  
#include <wchar.h>  
#include <errno.h>  
  
#define MB_BUFFER_SIZE 100  
  
int main()  
{  
    const wchar_t   wcString[] =   
                    {L"Every good boy does fine."};  
    const wchar_t   *wcsIndirectString = wcString;  
    char            mbString[MB_BUFFER_SIZE];  
    size_t          countConverted;  
    mbstate_t       mbstate;  
  
    // Reset to initial shift state  
    ::memset((void*)&mbstate, 0, sizeof(mbstate));  
  
    countConverted = wcsrtombs(mbString, &wcsIndirectString,  
                               MB_BUFFER_SIZE, &mbstate); // C4996  
    // Note: wcsrtombs is deprecated; consider using wcsrtombs_s  
    if (errno == EILSEQ)  
    {  
        printf( "An encoding error was detected in the string.\n" );  
    }  
    else   
    {  
        printf( "The string was successfuly converted.\n" );  
    }  
}  
```  
  
```Output  
The string was successfuly converted.  
```  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`wcsrtombs`|\<wchar.h>|  
  
## <a name="see-also"></a>См. также  
 [Преобразование данных](../../c-runtime-library/data-conversion.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)   
 [Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)   
 [wcrtomb](../../c-runtime-library/reference/wcrtomb.md)   
 [wcrtomb_s](../../c-runtime-library/reference/wcrtomb-s.md)   
 [wctomb, _wctomb_l](../../c-runtime-library/reference/wctomb-wctomb-l.md)   
 [wcstombs, _wcstombs_l](../../c-runtime-library/reference/wcstombs-wcstombs-l.md)   
 [mbsinit](../../c-runtime-library/reference/mbsinit.md)