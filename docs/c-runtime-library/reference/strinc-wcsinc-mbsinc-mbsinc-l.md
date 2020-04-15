---
title: _strinc, _wcsinc, _mbsinc, _mbsinc_l
ms.date: 4/2/2020
api_name:
- _mbsinc
- _wcsinc
- _mbsinc_l
- _strinc
- _o__mbsinc
- _o__mbsinc_l
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
- mbsinc_l
- _strinc
- strinc
- _mbsinc
- _wcsinc
- wcsinc
- mbsinc
- _mbsinc_l
helpviewer_keywords:
- _mbsinc function
- wcsinc function
- mbsinc_l function
- _strinc function
- strinc function
- _mbsinc_l function
- mbsinc function
- _wcsinc function
- _tcsinc function
- tcsinc function
ms.assetid: 54685943-8e2c-45e9-a559-2d94930dc6b4
ms.openlocfilehash: 0cfbe857ec8bbcdec887d4594cee0bf2b66de380
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81362908"
---
# <a name="_strinc-_wcsinc-_mbsinc-_mbsinc_l"></a>_strinc, _wcsinc, _mbsinc, _mbsinc_l

Увеличивает строковый указатель на один символ.

> [!IMPORTANT]
> **_mbsinc** и **_mbsinc_l** не могут быть использованы в приложениях, выполняемых в Windows Runtime. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
char *_strinc(
   const char *current,
   _locale_t locale
);
wchar_t *_wcsinc(
   const wchar_t *current,
   _locale_t locale
);
unsigned char *_mbsinc(
   const unsigned char *current
);
unsigned char *_mbsinc_l(
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Текущего*<br/>
Указатель символа.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Каждая из этих процедур возвращает указатель на символ, который сразу же следует *за течением.*

## <a name="remarks"></a>Remarks

**Функция _mbsinc** возвращает указатель на первый байт мультибайтного символа, который сразу же следует *за течением.* **_mbsinc** распознает последовательности мультибайт-символов в соответствии со [страницой мультибайткода,](../../c-runtime-library/code-pages.md) которая используется в настоящее время; **_mbsinc_l** идентичен, за исключением того, что вместо этого он использует параметр локализации, который передается в. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

Функция общего текста **_tcsinc,** определенная в Tchar.h, карты **для _mbsinc,** если **_MBCS** была определена, или **для _wcsinc,** если **_UNICODE** было определено. В противном случае, **_tcsinc** карты для **_strinc**. **_strinc** и **_wcsinc** являются однобайными и широкохарактерными версиями **_mbsinc.** **_strinc** и **_wcsinc** предоставляются только для этого отображения и не должны использоваться в противном случае. Дополнительные сведения см. в разделах [Использование универсальных текстовых сопоставлений](../../c-runtime-library/using-generic-text-mappings.md) и [Универсальные текстовые сопоставления](../../c-runtime-library/generic-text-mappings.md).

Если *ток* **NULL,** вызовуется обработчик параметров недействительного, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эта функция возвращает **EINVAL** и устанавливает **errno** **в EINVAL.**

> [!IMPORTANT]
> Эти функции могут быть подвержены угрозам переполнения буфера. Переполнение буфера можно использовать для атак на систему, поскольку оно может привести к несанкционированному повышению уровня привилегий. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbsinc**|\<mbstring.h>|
|**_mbsinc_l**|\<mbstring.h>|
|**_strinc**|\<tchar.h>|
|**_wcsinc**|\<tchar.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Манипуляция строками](../../c-runtime-library/string-manipulation-crt.md)<br/>
[_strdec, _wcsdec, _mbsdec, _mbsdec_l](strdec-wcsdec-mbsdec-mbsdec-l.md)<br/>
[_strnextc, _wcsnextc, _mbsnextc, _mbsnextc_l](strnextc-wcsnextc-mbsnextc-mbsnextc-l.md)<br/>
[_strninc, _wcsninc, _mbsninc, _mbsninc_l](strninc-wcsninc-mbsninc-mbsninc-l.md)<br/>
