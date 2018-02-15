---
title: "mbrlen | Документы Майкрософт"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: reference
apiname:
- mbrlen
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- mbrlen
dev_langs:
- C++
helpviewer_keywords:
- mbrlen function
ms.assetid: dde8dee9-e091-4c4c-81b3-639808885ae1
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c5c110c1fc5917614514b4e4fd7e474569026207
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="mbrlen"></a>mbrlen
Определяют число байтов, необходимое для составления многобайтового символа в текущем языковом стандарте, с возможностью перезапуска в середине многобайтового символа.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
size_t mbrlen(  
   const char * str,  
   size_t count,  
   mbstate_t * mbstate  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `str`  
 Указатель на следующий байт для проверки в строке многобайтовых символов.  
  
 `count`  
 Максимальное число байтов для проверки.  
  
 `mbstate`  
 Указатель на текущее состояние сдвига начального байта `str`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Одно из следующих значений:  
  
 0  
 Если следующие `count` или менее байт составляют многобайтовый символ, представляющий расширенный нуль-символ.  
  
 от 1 до `count` включительно  
 Если следующие `count` или менее байт составляют допустимый многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ.  
  
 (size_t)(-2)  
 Если следующие `count` байт складываются в неполный, но потенциально допустимый многобайтовый символ и все байты `count` были обработаны.  
  
 (size_t)(-1)  
 Произошла ошибка кодирования. Следующие `count` или менее байт не составляют полный и допустимый многобайтовый символ. В этом случае для `errno` будет установлено значение EILSEQ, а состояние преобразования в `mbstate` будет не определено.  
  
## <a name="remarks"></a>Примечания  
 Функция `mbrlen` проверяет не более `count` байт, начиная с байта, на который указывает параметр `str`, для определения числа байтов, необходимых для составления следующего многобайтового символа, включая любые последовательности сдвигов. Она эквивалентна вызову `mbrtowc(NULL, str, count, &mbstate)`, где `mbstate` — это либо предоставленный пользователем объект `mbstate_t`, либо статический внутренний объект, предоставленный библиотекой.  
  
 Функция `mbrlen` сохраняет и использует состояние сдвига неполного многобайтового символа в параметре `mbstate`. Это дает функции `mbrlen` возможность перезапуска в середине многобайтового символа в случае такой необходимости и проверки до `count` байтов. Если `mbstate` является пустым указателем, `mbrlen` использует внутренний статичный объект `mbstate_t` для хранения состояния сдвига. Так как внутренний объект `mbstate_t` не является потокобезопасным, мы рекомендуем всегда сохранять и передавать собственный параметр `mbstate`.  
  
 Функция `mbrlen` отличается от функций [_mbclen, mblen, _mblen_l](../../c-runtime-library/reference/mbclen-mblen-mblen-l.md) возможностью перезапуска. Состояние сдвига хранится в переменной `mbstate` для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, в приложении необходимо использовать функцию `wcsrlen` вместо функции `wcslen`, если в последующем вызове используется функция `wcsrtombs`, а не функция `wcstombs.`  
  
### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций  
  
|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|  
|---------------------|------------------------------------|--------------------|-----------------------|  
|Неприменимо|Неприменимо|`mbrlen`|Неприменимо|  
  
## <a name="requirements"></a>Требования  
  
|Подпрограмма|Обязательный заголовок|  
|-------------|---------------------|  
|`mbrlen`|\<wchar.h>|  
  
 Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md) во введении.  
  
## <a name="example"></a>Пример  
 В этом примере показано, как интерпретация многобайтовых символов зависит от текущей кодовой страницы, и демонстрируется возможность продолжения выполнения функции `mbrlen`.  
  
```C  
// crt_mbrlen.c  
// Compile by using: cl crt_mbrlen.c  
#include <stdlib.h>  
#include <stdio.h>  
#include <string.h>  
#include <locale.h>  
#include <wchar.h>  
  
size_t Example(const char * pStr)  
{  
    size_t      charLen = 0;  
    size_t      charCount = 0;  
    mbstate_t   mbState = {0};  
  
    while ((charLen = mbrlen(pStr++, 1, &mbState)) != 0 &&  
            charLen != (size_t)-1)  
    {  
        if (charLen != (size_t)-2) // if complete mbcs char,  
        {  
            charCount++;  
        }  
    }   
    return (charCount);  
}   
  
int main( void )  
{  
    int         cp;  
    size_t      charCount = 0;  
    const char  *pSample =   
        "\x82\xD0\x82\xE7\x82\xAA\x82\xC8: Shift-jis hiragana.";  
  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
  
    setlocale(LC_ALL, "ja-JP"); // Set Japanese locale  
    _setmbcp(932); // and Japanese multibyte code page  
    cp = _getmbcp();  
    charCount = Example(pSample);  
    printf("\nCode page: %d\n%s\nCharacter count: %d\n",   
        cp, pSample, charCount);  
}  
```  
  
```Output  
  
Code page: 0  
é╨éτé¬é╚: Shift-jis hiragana.  
Character count: 29  
  
Code page: 932  
????: Shift-jis hiragana.  
Character count: 25  
  
```  
  
## <a name="see-also"></a>См. также  
 [Операции со строками](../../c-runtime-library/string-manipulation-crt.md)   
 [Языковой стандарт](../../c-runtime-library/locale.md)