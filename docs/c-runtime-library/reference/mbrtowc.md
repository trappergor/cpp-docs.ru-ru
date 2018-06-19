---
title: mbrtowc | Документы Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-standard-libraries
ms.topic: reference
apiname:
- mbrtowc
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
- mbrtowc
dev_langs:
- C++
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 256c3df754607d0d9321f87d565e2ce94491035c
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32405319"
---
# <a name="mbrtowc"></a>mbrtowc

Преобразуют многобайтовый символ в текущем языковом стандарте в эквивалентный расширенный символ с возможностью перезапуска в середине многобайтового символа.

## <a name="syntax"></a>Синтаксис

```C
size_t mbrtowc(
   wchar_t *wchar,
   const char *mbchar,
   size_t count,
   mbstate_t *mbstate
);
```

### <a name="parameters"></a>Параметры

*wchar*<br/>
Адрес расширенного символа для получения преобразованной строки расширенных символов (тип **wchar_t**). Это значение может быть пустым указателем, если не требуется возвращать расширенный символ.

*mbchar*<br/>
Адрес последовательности байтов (многобайтовый символ).

*count*<br/>
Число проверяемых байтов.

*mbstate*<br/>
Указатель на объект состояния преобразования. Если это значение является пустым указателем, функция использует статичный внутренний объект состояния преобразования. Так как внутренний **mbstate_t** объект не является потокобезопасным, мы рекомендуем всегда передавать собственный *mbstate* аргумент.

## <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

0 следующего *число* или менее байт составляют Многобайтовый символ, представляющий расширенный символ null, которое хранится в *wchar*, если *wchar* не является указателем null.

от 1 до *число*включительно следующего *число* или менее байт составляют допустимый Многобайтовый символ. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ. Эквивалентный расширенный символ хранится в *wchar*, если *wchar* не является указателем null.

(size_t) (-1) Произошла ошибка кодирования. Следующий *число* или менее байт не составляют полный и допустимый Многобайтовый символ. В этом случае **errno** задано значение EILSEQ, а состояние сдвига преобразования в *mbstate* не указан.

(size_t) -(2) Следующий *число* байт складываются в неполный, но потенциально допустимый Многобайтовый символ и все *число* байтов будут обработаны. Значение не хранится в *wchar*, но *mbstate* обновляется для перезапуска функции.

## <a name="remarks"></a>Примечания

Если *mbchar* является пустым указателем, функция эквивалентна вызову:

`mbrtowc(NULL, "", 1, &mbstate)`

В этом случае значение аргументов *wchar* и *число* игнорируются.

Если *mbchar* не является пустым указателем, функция проверяет *число* байтов из *mbchar* определить требуемое количество байтов, необходимое для выполнения следующего Многобайтовый символ. Если следующий символ является допустимым, соответствующий Многобайтовый символ сохраняется в *wchar* Если это не является пустым указателем. Если символ соответствует расширенному нуль символов, результирующее состояние *mbstate* является начальным состоянием преобразования.

**Mbrtowc** функция отличается от [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) возможностью перезапуска. Состояние преобразования хранится в *mbstate* для последующих вызовов тех же или других перезапускаемых функций. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **wcsrlen** вместо **wcslen** при последующих вызовах **wcsrtombs** используется вместо **wcstombs**.

## <a name="example"></a>Пример

Преобразует многобайтовый символ в эквивалентный расширенный символ.

```cpp
// crt_mbrtowc.cpp

#include <stdio.h>
#include <mbctype.h>
#include <string.h>
#include <locale.h>
#include <wchar.h>

#define BUF_SIZE 100

int Sample(char* szIn, wchar_t* wcOut, int nMax)
{
    mbstate_t   state = {0}; // Initial state
    size_t      nConvResult,
                nmbLen = 0,
                nwcLen = 0;
    wchar_t*    wcCur = wcOut;
    wchar_t*    wcEnd = wcCur + nMax;
    const char* mbCur = szIn;
    const char* mbEnd = mbCur + strlen(mbCur) + 1;
    char*       szLocal;

    // Sets all locale to French_Canada.1252
    szLocal = setlocale(LC_ALL, "French_Canada.1252");
    if (!szLocal)
    {
        printf("The fuction setlocale(LC_ALL, \"French_Canada.1252\") failed!\n");
        return 1;
    }

    printf("Locale set to: \"%s\"\n", szLocal);

    // Sets the code page associated current locale's code page
    // from a previous call to setlocale.
    if (_setmbcp(_MB_CP_SBCS) == -1)
    {
        printf("The fuction _setmbcp(_MB_CP_SBCS) failed!");
        return 1;
    }

    while ((mbCur < mbEnd) && (wcCur < wcEnd))
    {
        //
        nConvResult = mbrtowc(wcCur, mbCur, 1, &state);
        switch (nConvResult)
        {
            case 0:
            {  // done
                printf("Conversion succeeded!\nMultibyte String: ");
                printf(szIn);
                printf("\nWC String: ");
                wprintf(wcOut);
                printf("\n");
                mbCur = mbEnd;
                break;
            }

            case -1:
            {  // encoding error
                printf("The call to mbrtowc has detected an encoding error.\n");
                mbCur = mbEnd;
                break;
            }

            case -2:
            {  // incomplete character
                if   (!mbsinit(&state))
                {
                    printf("Currently in middle of mb conversion, state = %x\n", state);
                    // state will contain data regarding lead byte of mb character
                }

                ++nmbLen;
                ++mbCur;
                break;
            }

            default:
            {
                if   (nConvResult > 2) // The multibyte should never be larger than 2
                {
                    printf("Error: The size of the converted multibyte is %d.\n", nConvResult);
                }

                ++nmbLen;
                ++nwcLen;
                ++wcCur;
                ++mbCur;
            break;
            }
        }
    }

   return 0;
}

int main(int argc, char* argv[])
{
    char    mbBuf[BUF_SIZE] = "AaBbCc\x9A\x8B\xE0\xEF\xF0xXyYzZ";
    wchar_t wcBuf[BUF_SIZE] = {L''};

    return Sample(mbBuf, wcBuf, BUF_SIZE);
}
```

### <a name="sample-output"></a>Пример результатов выполнения

```Output
Locale set to: "French_Canada.1252"
Conversion succeeded!
Multibyte String: AaBbCcÜïα∩≡xXyYzZ
WC String: AaBbCcÜïα∩≡xXyYzZ
```

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**mbrtowc**|\<wchar.h>|

## <a name="see-also"></a>См. также

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
