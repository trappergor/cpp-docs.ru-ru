---
title: _ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l
ms.date: 4/2/2020
api_name:
- _ismbstrail
- _ismbslead_l
- _ismbslead
- _ismbstrail_l
- _o__ismbslead
- _o__ismbslead_l
- _o__ismbstrail
- _o__ismbstrail_l
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
- _ismbslead
- ismbs
- ismbslead_l
- _ismbs
- ismbstrail_l
- ismbslead
- _ismbstrail
- _ismbstrail_l
- ismbstrail
- _ismbslead_l
helpviewer_keywords:
- ismbstrail function
- _ismbslead function
- ismbslead function
- ismbslead_l function
- _ismbstrail function
- _ismbslead_l function
- ismbstrail_l function
- _ismbstrail_l function
ms.assetid: 86d2cd7a-3cff-443a-b713-14cc17a231e9
ms.openlocfilehash: d4c9bfcec1deab8c00eb490dc044e62a6124aba3
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81342914"
---
# <a name="_ismbslead-_ismbstrail-_ismbslead_l-_ismbstrail_l"></a>_ismbslead, _ismbstrail, _ismbslead_l, _ismbstrail_l

Выполняет контекстно-зависимые тесты для старших и младших байтов многобайтовой символьной строки и определяет, указывает ли указатель данной подстроки старший или младший байт.

> [!IMPORTANT]
> Этот API нельзя использовать в приложениях, выполняемых в среде выполнения Windows. Дополнительные сведения: [Функции CRT, которые не поддерживаются в приложениях универсальной платформы Windows](../../cppcx/crt-functions-not-supported-in-universal-windows-platform-apps.md).

## <a name="syntax"></a>Синтаксис

```C
int _ismbslead(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbstrail(
   const unsigned char *str,
   const unsigned char *current
);
int _ismbslead_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
int _ismbstrail_l(
   const unsigned char *str,
   const unsigned char *current,
   _locale_t locale
);
```

### <a name="parameters"></a>Параметры

*Ул*<br/>
Указатель на начало строки или на предыдущий известный старший байт.

*Текущего*<br/>
Указатель на позицию в строке, которую нужно протестировать.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_ismbslead** возвращает -1, если персонаж является свинцово-_ismbstrail **возвращает** -1, если персонаж является следом байт. Если входные строки допустимы, но не являются старшим или младшим байтом, эти функции возвращают ноль. Если какой-либо аргумент является **NULL,** вызовуется обработчик параметров, как описано в [проверке параметра.](../../c-runtime-library/parameter-validation.md) Если выполнение разрешено продолжать, эти функции возвращают **NULL** и устанавливают **errno** **в EINVAL.**

## <a name="remarks"></a>Remarks

**_ismbslead** и **_ismbstrail** медленнее, чем **_ismbblead** и **_ismbbtrail** версии, поскольку они принимают во внимание контекст строки.

Версии этих функций, которые имеют **_l** суффикс идентичны, за исключением того, что для их локально-зависимого поведения они используют локали, которое передается в вместо текущего локализации. Для получения дополнительной информации см. [Locale](../../c-runtime-library/locale.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|Необязательный заголовок|
|-------------|---------------------|---------------------|
|**_ismbslead**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbslead_l**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|
|**_ismbstrail_l**|\<mbctype.h> или \<mbstring.h>|\<ctype.h>,* \<limits.h>, \<stdlib.h>|

\* Для констант манифестов, используемых в условиях проверки.

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="see-also"></a>См. также раздел

[Классификация символов](../../c-runtime-library/character-classification.md)<br/>
[Процедуры _ismbc](../../c-runtime-library/ismbc-routines.md)<br/>
[Процедуры is, isw](../../c-runtime-library/is-isw-routines.md)<br/>
[_ismbb рутины](../../c-runtime-library/ismbb-routines.md)<br/>
