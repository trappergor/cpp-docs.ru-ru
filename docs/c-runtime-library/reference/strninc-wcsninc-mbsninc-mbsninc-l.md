---
title: _strninc, _wcsninc, _mbsninc, _mbsninc_l
ms.date: 11/04/2016
apiname:
- _mbsninc
- _mbsninc_l
- _wcsninc
- _strninc
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
- api-ms-win-crt-multibyte-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- strninc
- wcsninc
- mbsninc_l
- _strninc
- _tcsninc
- mbsninc
- _mbsninc_l
- _ftcsninc
- _wcsninc
- _mbsninc
helpviewer_keywords:
- _mbsninc_l function
- mbsninc function
- _strninc function
- tcsninc function
- wcsninc function
- _mbsninc function
- strninc function
- _wcsninc function
- mbsninc_l function
- _tcsninc function
ms.assetid: 6caace64-f9e4-48c0-afa8-ea51824ad723
ms.openlocfilehash: ef30a9f57f0b8c84199befb00f3edc13342a1eaf
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50643187"
---
# <a name="strninc-wcsninc-mbsninc-mbsnincl"></a>_strninc, _wcsninc, _mbsninc, _mbsninc_l

Увеличивает строковый указатель по **n** символов.

> [!IMPORTANT]
> **_mbsninc** и **_mbsninc_l** нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strninc(
   const char *str,
   size_t count
);
wchar_t *_wcsninc(
   const wchar_t *str,
   size_t count
);
unsigned char *_mbsninc(
   const unsigned char *str,
   size_t count
);
unsigned char *_mbsninc(
   const unsigned char *str,
   size_t count,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*str*<br/>
Исходная строка.

*count*<br/>
Количество символов, на которые увеличивается указатель на строку.

*locale*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих подпрограмм возвращает указатель на *str* после *str* был увеличен на *число* символов или **NULL** если предоставленный указатель находится **NULL**. Если *число* больше или равно числу символов в *str*, результат не определен.

## <a name="remarks"></a>Примечания

**_Mbsninc** работать с шагом *str* по *число* многобайтовых символов. **_mbsninc** распознает последовательности многобайтовых символов в соответствии с [многобайтовую кодовую страницу](../../c-runtime-library/code-pages.md) в настоящий момент.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tcsninc**|**_strninc**|**_mbsninc**|**_wcsninc**|

**_strninc** и **_wcsninc** -однобайтовыми строки и версий строки расширенных символов **_mbsninc**. **_wcsninc** и **_strninc** предоставляются только для этого сопоставления и не должны использоваться в противном случае. Дополнительные сведения см. в разделах [Использование универсальных текстовых сопоставлений](../../c-runtime-library/using-generic-text-mappings.md) и [Универсальные текстовые сопоставления](../../c-runtime-library/generic-text-mappings.md).

**_mbsninc_l** идентична за исключением того, что она использует переданный параметр языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsninc**|\<mbstring.h>|
|**_mbsninc_l**|\<mbstring.h>|
|**_strninc**|\<tchar.h>|
|**_wcsninc**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Операции со строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strinc, _wcsinc, _mbsinc, _mbsinc_l](strinc-wcsinc-mbsinc-mbsinc-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
