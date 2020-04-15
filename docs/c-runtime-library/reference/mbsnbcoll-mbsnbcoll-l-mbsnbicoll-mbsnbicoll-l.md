---
title: _mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l
ms.date: 4/2/2020
api_name:
- _mbsnbicoll_l
- _mbsnbcoll_l
- _mbsnbcoll
- _mbsnbicoll
- _o__mbsnbcoll
- _o__mbsnbcoll_l
- _o__mbsnbicoll
- _o__mbsnbicoll_l
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
- api-ms-win-crt-multibyte-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _mbsnbcoll
- _mbsnbcoll_l
- _mbsnbicoll
- mbsnbcoll_l
helpviewer_keywords:
- _mbsnbcoll_l function
- mbsnbcoll_l function
- _mbsnbcoll function
- _tcsnicoll function
- mbsnbcoll function
- mbsnbicoll_l function
- mbsnbicoll function
- _tcsncoll function
- _mbsnbicoll function
- _mbsnbicoll_l function
- _tcsncoll_l function
- _tcsnicoll_l function
ms.assetid: d139ed63-ccba-4458-baa2-61cbcef03e94
ms.openlocfilehash: 0b02a34f9b721e4cfcf07ac3679d0dce166a4ff7
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81340743"
---
# <a name="_mbsnbcoll-_mbsnbcoll_l-_mbsnbicoll-_mbsnbicoll_l"></a>_mbsnbcoll, _mbsnbcoll_l, _mbsnbicoll, _mbsnbicoll_l

Сравнивает *n* байты двух строк с мультибайт-символами, используя информацию о многобайтной код-странице.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _mbsnbcoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbcoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
int _mbsnbicoll(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count
);
int _mbsnbicoll_l(
   const unsigned char *string1,
   const unsigned char *string2,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*string1*, *string2*<br/>
Строки для сравнения.

*count*<br/>
Число сравниваемых байтов.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Значение возврата указывает на отношение подстроек *строки1* и *строки2.*

|Возвращаемое значение|Описание|
|------------------|-----------------|
|< 0|*string1* подстроки меньше, чем *подстрока2.*|
|0|*string1* подстроки, идентичной *подстроке2.*|
|> 0|*string1* подстроки больше, чем *подстрока string2.*|

Если *string1* или *string2* **null** или *количество* больше, чем **INT_MAX,** вызовуется обработчик параметров недействительного, как описано в [проверке параметров.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции возвращают **_NLSCMPERROR** и установить **errno** к **EINVAL**. Для использования **_NLSCMPERROR,** включают либо String.h или Mbstring.h.

## <a name="remarks"></a>Remarks

Каждая из этих функций сопоставляют, в лучшем случае, первые *байты в* *string1* и *string2* и возвращает значение, указывающее на связь между полученными подстроками *string1* и *string2.* Если финальный байт в подстроке *строки1* или *строки2* является свинцовой байтом, он не входит в сравнение; эти функции сравнивают только полные символы в подстроках. **_mbsnbicoll** является нечувствительной версией **_mbsnbcoll.** Как [_mbsnbcmp](mbsnbcmp-mbsnbcmp-l.md) и [_mbsnbicmp,](mbsnbicmp-mbsnbicmp-l.md) **_mbsnbcoll** и **_mbsnbicoll** составить две строки мультибайт-символа в соответствии с лексикографическим порядком, указанным в основе страницы мультибайтного [кода,](../../c-runtime-library/code-pages.md) которая в настоящее время используется.

Для некоторых кодовых страниц и соответствующих наборов символов порядок символов в наборе может отличаться от лексикографического порядка символов. Языковой стандарт "C" не входит в их число: порядок символов в кодировке ASCII совпадает с лексикографическим порядком символов. Однако, в некоторых европейских языковых стандартах, например, символ "a" (значение 0x61) предшествует символу "ä" (значение 0xE4) в кодировке, но "ä" предшествует символу "a" лексикографически. Для выполнения лексикографического сравнения строк байтами в таком случае используйте **_mbsnbcoll,** а не **_mbsnbcmp;** чтобы проверить только на равенство строк, использовать **_mbsnbcmp**.

Поскольку **функции коллажа** сопоставления строк лексикографически для сравнения, в то время как функции **cmp** просто проверяются на равенство строк, функции **колла** намного медленнее, чем соответствующие версии **Cmp.** Таким образом, **функции колла** должны использоваться только тогда, когда есть разница между порядком набора символов и лексикографическим порядком символов на текущей странице кода, и эта разница представляет интерес для сравнения.

Выходное значение зависит от настройки категории **LC_CTYPE** языкового стандарта; дополнительные сведения см. в разделе [setlocale](setlocale-wsetlocale.md). Версии этих функций без суффикса **_l** используют текущий языковой стандарт для данного поведения, зависящего от языкового стандарта; версии с суффиксом **_l** идентичны, за исключением того, что они используют переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsncoll**|[_strncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll**|[_wcsncoll](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsncoll_l**|[_strncoll, _wcsncoll, _mbsncoll, _strncoll_l, _wcsncoll_l, _mbsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|**_mbsnbcoll_l**|[_wcsncoll_l](strncoll-wcsncoll-mbsncoll-strncoll-l-wcsncoll-l-mbsncoll-l.md)|
|**_tcsnicoll**|[_strnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll**|[_wcsnicoll](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|
|**_tcsnicoll_l**|[_strnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|**_mbsnbicoll_l**|[_wcsnicoll_l](strnicoll-wcsnicoll-mbsnicoll-strnicoll-l-wcsnicoll-l-mbsnicoll-l.md)|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsnbcoll**|\<mbstring.h>|
|**_mbsnbcoll_l**|\<mbstring.h>|
|**_mbsnbicoll**|\<mbstring.h>|
|**_mbsnbicoll_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_mbsnbcat, _mbsnbcat_l](mbsnbcat-mbsnbcat-l.md)<br/>
[_mbsnbcmp, _mbsnbcmp_l](mbsnbcmp-mbsnbcmp-l.md)<br/>
[_mbsnbicmp, _mbsnbicmp_l](mbsnbicmp-mbsnbicmp-l.md)<br/>
[strcoll Functions](../../c-runtime-library/strcoll-functions.md)<br/>
[strncmp, wcsncmp, _mbsncmp, _mbsncmp_l](strncmp-wcsncmp-mbsncmp-mbsncmp-l.md)<br/>
[_strnicmp, _wcsnicmp, _mbsnicmp, _strnicmp_l, _wcsnicmp_l, _mbsnicmp_l](strnicmp-wcsnicmp-mbsnicmp-strnicmp-l-wcsnicmp-l-mbsnicmp-l.md)<br/>
