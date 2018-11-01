---
title: _mbccpy, _mbccpy_l
ms.date: 11/04/2016
apiname:
- _mbccpy
- _mbccpy_l
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
- _mbccpy
- tccpy
- ftccpy
- mbccpy
- _tccpy
- _ftccpy
helpviewer_keywords:
- _tccpy function
- _tccpy_l function
- tccpy_l function
- tccpy function
- mbccpy function
- _mbccpy_l function
- _mbccpy function
- mbccpy_l function
ms.assetid: 13f4de6e-7792-41ac-b319-dd9b135433aa
ms.openlocfilehash: 852097ebea41ef99b1a53f7bc344eb0c08911a4d
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50533748"
---
# <a name="mbccpy-mbccpyl"></a>_mbccpy, _mbccpy_l

Копирует многобайтовый символ из одной строки в другую. Существуют более безопасные версии этих функций; см. раздел [_mbccpy_s, _mbccpy_s_l](mbccpy-s-mbccpy-s-l.md).

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
void _mbccpy(
   unsigned char *dest,
   const unsigned char *src
);
void _mbccpy_l(
   unsigned char *dest,
   const unsigned char *src,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*dest*<br/>
Место назначения копирования.

*src*<br/>
Многобайтовый символ для копирования.

*locale*<br/>
Используемый языковой стандарт.

## <a name="remarks"></a>Примечания

**_Mbccpy** функция копирует один Многобайтовый символ из *src* для *dest*.

Эта функция проверяет свои параметры. Если **_mbccpy** передается указатель null *dest* или *src*, вызывается обработчик недопустимого параметра, как описано в разделе [проверка параметров](../../c-runtime-library/parameter-validation.md). Если выполнение может быть продолжено, **errno** присваивается **EINVAL**.

**_mbccpy** использует текущий языковой стандарт для любого поведения, зависящего от языкового стандарта. **_mbccpy_l** идентична **_mbccpy** за исключением того, что **_mbccpy_l** использует переданный параметр языкового стандарта для любого поведения, зависящего от языкового стандарта. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

**Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Длина строки, завершающейся нуль-символом, не должна превышать размер буфера назначения. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/desktop/SecBP/avoiding-buffer-overruns). Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав.

### <a name="generic-text-routine-mappings"></a>Сопоставления подпрограмм обработки обычного текста

|Подпрограмма Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Сопоставляется макросу или встраиваемой функции|**_mbccpy**|Сопоставляется макросу или встраиваемой функции|
|**_tccpy_l**|Н/Д|**_mbccpy_l**|Н/Д|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Совместимость](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также

[Языковой стандарт](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
