---
title: _mbbtombc, _mbbtombc_l
ms.date: 4/2/2020
api_name:
- _mbbtombc_l
- _mbbtombc
- _o__mbbtombc
- _o__mbbtombc_l
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
- _mbbtombc_l
- _mbbtombc
- mbbtombc_l
- mbbtombc
helpviewer_keywords:
- mbbtombc_l function
- mbbtombc function
- _mbbtombc_l function
- _mbbtombc function
ms.assetid: 78593389-b0fc-43b6-8c1f-2a6bf702d64e
ms.openlocfilehash: 5d26b06da1dcf8c53abda5d4ff2ee06ec3e7cd11
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81341416"
---
# <a name="_mbbtombc-_mbbtombc_l"></a>_mbbtombc, _mbbtombc_l

Преобразует однобайтовый многобайтовый символ в соответствующий двухбайтовый многобайтовый символ.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
unsigned int _mbbtombc(
   unsigned int c
);
unsigned int _mbbtombc_l(
   unsigned int c,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Однобайтовый символ, который необходимо преобразовать.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

Если **_mbbtombc** успешно преобразует *c,* он возвращает мультибайтный символ; в противном случае, он возвращает *c*.

## <a name="remarks"></a>Remarks

Функция **_mbbtombc** преобразует данный однобайный мультибайтный символ в соответствующий двухбайтный мультибайтный символ. Персонажи должны быть в пределах диапазона 0x20 - 0x7E или 0xA1 - 0xDF для преобразования.

На значение вывода влияет настройка **LC_CTYPE** категории локализуем; см [setlocale, _wsetlocale](setlocale-wsetlocale.md) для получения дополнительной информации. Версии этой функции идентичны, за исключением того, что **_mbbtombc** использует текущий локаль для этого поведения, зависящем от локального, и вместо этого **_mbbtombc_l** использует параметр локализации, который передается. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

В более ранних **версиях, _mbbtombc** был назван **hantozen**. Для нового кода используйте **_mbbtombc**.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_mbbtombc**|\<mbstring.h>|
|**_mbbtombc_l**|\<mbstring.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Преобразование данных](../../c-runtime-library/data-conversion.md)<br/>
[_mbctombb, _mbctombb_l](mbctombb-mbctombb-l.md)<br/>
