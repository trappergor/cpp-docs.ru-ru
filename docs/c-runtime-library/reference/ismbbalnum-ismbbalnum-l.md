---
title: _ismbbalnum, _ismbbalnum_l
ms.date: 4/2/2020
api_name:
- _ismbbalnum
- _ismbbalnum_l
- _o__ismbbalnum
- _o__ismbbalnum_l
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
- _ismbbalnum
- ismbbalnum
- _ismbbalnum_l
- ismbbalnum_l
helpviewer_keywords:
- _ismbbalnum_l function
- ismbbalnum function
- ismbbalnum_l function
- _ismbbalnum function
ms.assetid: 8025de50-a871-49fd-9ae6-f437b47aa987
ms.openlocfilehash: 3a200415571498c25ce5aacc6271004125ef16d2
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81343696"
---
# <a name="_ismbbalnum-_ismbbalnum_l"></a>_ismbbalnum, _ismbbalnum_l

Определяет, является ли указанный многобайтовый символ буквой или цифрой.

## <a name="syntax"></a>Синтаксис

```C
int _ismbbalnum(
   unsigned int c
);
int _ismbbalnum_l(
   unsigned int c
);
```

### <a name="parameters"></a>Параметры

*C*<br/>
Целое число, которое требуется проверить.

*Языкового стандарта*<br/>
Используемый языковой стандарт.

## <a name="return-value"></a>Возвращаемое значение

**_ismbbalnum** возвращает ненулевое значение, если выражение:

`isalnum(c) || _ismbbkalnum(c)`

является незерной для *c,* или 0, если это не так.

Версия этой функции с **_l** суффикса идентична, за исключением того, что она использует локали, передаваемую в вместо текущего локаль для его локально-зависимого поведения.

## <a name="remarks"></a>Remarks

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](../global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|**_ismbbalnum**|\<mbctype.h>|
|**_ismbbalnum_l**|\<mbctype.h>|

Дополнительные сведения о совместимости см. в разделе [Compatibility](../../c-runtime-library/compatibility.md).

## <a name="libraries"></a>Библиотеки

Все версии [библиотек времени выполнения языка C](../../c-runtime-library/crt-library-features.md).

## <a name="see-also"></a>См. также раздел

[Классификация байтов](../../c-runtime-library/byte-classification.md)<br/>
[_ismbb рутины](../../c-runtime-library/ismbb-routines.md)<br/>
