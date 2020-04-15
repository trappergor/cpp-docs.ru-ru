---
title: _mbccpy, _mbccpy_l
ms.date: 4/2/2020
api_name:
- _mbccpy
- _mbccpy_l
- _o__mbccpy
- _o__mbccpy_l
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
ms.openlocfilehash: 45f93e370e11cf38fc17da3557b21c636fcbc623
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341268"
---
# <a name="_mbccpy-_mbccpy_l"></a>_mbccpy, _mbccpy_l

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

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="remarks"></a>Remarks

**Функция _mbccpy** копирует один мультибайтный символ от *src* до *dest.*

Эта функция проверяет свои параметры. Если **_mbccpy** передается нулевой указатель для *dest* или *src,* недействительный обработчик параметров вызывается, как описано в [параметре валидации.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, **errno** устанавливается на **EINVAL**.

**_mbccpy** использует текущий локал для любого поведения, зависящем от локального. **_mbccpy_l** идентичен **_mbccpy** за исключением того, что **_mbccpy_l** использует локал, передаваемый для любого поведения, зависящем от локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

**Примечание о безопасности.** Следует использовать строку, оканчивающуюся нуль-символом. Длина строки, завершающейся нуль-символом, не должна превышать размер буфера назначения. Дополнительные сведения см. в разделе [Как избежать переполнения буфера](/windows/win32/SecBP/avoiding-buffer-overruns). Проблемы переполнения буфера — это распространенный метод атак на системы, который приводит к несанкционированному повышению уровня прав.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Процедура Tchar.h|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|--------------------------------------|--------------------|-----------------------|
|**_tccpy**|Сопоставляется макросу или встраиваемой функции|**_mbccpy**|Сопоставляется макросу или встраиваемой функции|
|**_tccpy_l**|Недоступно|**_mbccpy_l**|Недоступно|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbccpy**|\<mbctype.h>|
|**_mbccpy_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Локаль](../../c-runtime-library/locale.md)<br/>
[Интерпретация последовательностей многобайтовых символов](../../c-runtime-library/interpretation-of-multibyte-character-sequences.md)<br/>
[_mbclen, mblen, _mblen_l](mbclen-mblen-mblen-l.md)<br/>
