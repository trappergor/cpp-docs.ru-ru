---
title: isleadbyte, _isleadbyte_l
ms.date: 4/2/2020
api_name:
- _isleadbyte_l
- isleadbyte
- _o__isleadbyte_l
- _o_isleadbyte
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
- api-ms-win-crt-string-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _istleadbyte
- _isleadbyte_l
- isleadbyte
helpviewer_keywords:
- lead bytes
- _isleadbyte_l function
- _istleadbyte function
- istleadbyte function
- isleadbyte function
ms.assetid: 3b2bcf09-d82b-4803-9e80-59d04942802a
ms.openlocfilehash: dddf1d669f77805df8e00f506b6427603ac8fd9f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343838"
---
# <a name="isleadbyte-_isleadbyte_l"></a>isleadbyte, _isleadbyte_l

Определяет, является ли символ начальным байтом многобайтового символа.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int isleadbyte( int c );
int _isleadbyte_l( int c );
```

### <a name="parameters"></a>Параметры

*C*<br/>
Проверяемое целое число.

## <a name="return-value"></a>Возвращаемое значение

**isleadbyte** возвращает ненулевое значение, если аргумент удовлетворяет условие милизора или 0, если он этого не делает. В локаль "C" и в однобайном наборе символов **isleadbyte** (SBCS) всегда возвращается 0.

## <a name="remarks"></a>Remarks

**Макроисс ислидбайт** возвращает ненулевое значение, если его аргумент является первым байтом мультибайтного символа. **isleadbyte** дает значимый результат для любого рядового аргумента от -1 **(EOF)** до **UCHAR_MAX** (0xFF), включительно.

Ожидаемый тип аргумента **isleadbyte** **int;** если подписанный символ пройден, компилятор может преобразовать его в ряд ы расширением знака, что дает непредсказуемые результаты.

Версия этой функции с **_l** суффикса идентична, за исключением того, что она использует локали, передаваемую в вместо текущего локаль для его локально-зависимого поведения.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

### <a name="generic-text-routine-mappings"></a>Универсальное текстовое сопоставление функций

|Подпрограмма TCHAR.H|_UNICODE и _MBCS не определены|_MBCS определено|_UNICODE определено|
|---------------------|------------------------------------|--------------------|-----------------------|
|**_istleadbyte**|Всегда возвращает значение false|**_isleadbyte**|Всегда возвращает значение false|

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**isleadbyte**|\<ctype.h>|
|**_isleadbyte_l**|\<ctype.h>|

Дополнительные сведения о совместимости см. в статье [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[Локаль](../../c-runtime-library/locale.md)<br/>
[_ismbb рутины](../../c-runtime-library/ismbb-routines.md)<br/>
