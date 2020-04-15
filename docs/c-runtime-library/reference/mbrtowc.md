---
title: mbrtowc
ms.date: 4/2/2020
api_name:
- mbrtowc
- _o_mbrtowc
api_location:
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
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- mbrtowc
helpviewer_keywords:
- mbrtowc function
ms.assetid: a1e87fcc-6de0-4ca1-bf26-508d28490286
ms.openlocfilehash: be46c3f3c728b70c7cbf060572acc24662637a81
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340921"
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

*Wchar*<br/>
Адрес широкого характера для получения преобразованной широкой строки символов (тип **wchar_t).** Это значение может быть пустым указателем, если не требуется возвращать расширенный символ.

*mbchar*<br/>
Адрес последовательности байтов (многобайтовый символ).

*count*<br/>
Число проверяемых байтов.

*mbstate*<br/>
Указатель на объект состояния преобразования. Если это значение является пустым указателем, функция использует статичный внутренний объект состояния преобразования. Поскольку внутренний **mbstate_t** объект не является безопасным для потоков, мы рекомендуем вам всегда передавать свой собственный аргумент *mbstate.*

## <a name="return-value"></a>Возвращаемое значение

Одно из следующих значений:

0 Следующий *счет* или меньше байтов завершить мультибайт характер, который представляет нулевой широкий символ, который хранится в *wchar*, если *wchar* не является нулевой указатель.

1 для *подсчета,* включительно Следующий *счет* или меньше байтов завершить действительный мультибайт характер. Возвращаемое значение равно количеству байтов, составляющих многобайтовый символ. Широкий эквивалент характера хранится в *wchar,* если *wchar* не является нулевой указатель.

(size_t) (-1) Произошла ошибка кодирования. Следующий *подсчет* или меньше байт не способствуют полному и допустимому мультибайтному символу. В этом случае **errno** устанавливается в EILSE, а состояние изменения сдвига в *mbstate* не уточняется.

(size_t) (-2) Следующие байты *подсчета* способствуют неполному, но потенциально допустимому многобайтному символу, и все *байты подсчета* были обработаны. Никакое значение не хранится в *wchar,* но *mbstate* обновляется для перезапуска функции.

## <a name="remarks"></a>Remarks

Если *mbchar* является нулевой указатель, функция эквивалентна вызову:

`mbrtowc(NULL, "", 1, &mbstate)`

В этом случае значение аргументов *wchar* и *подсчета* игнорируются.

Если *mbchar* не является нулевой указатель, функция рассматривает *количество* байтов от *mbchar,* чтобы определить необходимое количество байтов, которые необходимы для завершения следующего мультибайтного символа. Если следующий символ действителен, соответствующий мультибайтный символ хранится в *wchar,* если он не является нулевой указателем. Если символ является соответствующим широким нулевая символом, то в результате состояние *mbstate* является исходное состояние преобразования.

Функция **mbrtowc** отличается от [mbtowc, _mbtowc_l](mbtowc-mbtowc-l.md) своей перезапуском. Состояние преобразования хранится в *mbstate* для последующих вызовов к тем же или другим перезажаемым функциям. При смешанном использовании перезапускаемых и неперезапускаемых функций результаты становятся неопределенными.  Например, приложение должно использовать **wcsrlen** вместо **wcslen,** если последующий вызов **wcsrtombs** используется вместо **wcstombs**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

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

### <a name="sample-output"></a>Пример выходных данных

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

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
