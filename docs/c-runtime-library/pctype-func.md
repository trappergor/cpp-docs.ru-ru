---
title: __pctype_func
ms.date: 4/2/2020
api_name:
- __pctype_func
- _o___pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
- api-ms-win-crt-private-l1-1-0
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: 78562a29c89abe5b649444ae9223cf219488e009
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349198"
---
# <a name="__pctype_func"></a>__pctype_func

Извлекает указатель на массив данных о классификации символов.

## <a name="syntax"></a>Синтаксис

```cpp
const unsigned short *__pctype_func(
   )
```

## <a name="return-value"></a>Возвращаемое значение

Указатель на массив данных о классификации символов.

## <a name="remarks"></a>Remarks

Сведения в таблице классификации символов предназначены только для внутреннего пользования и используются различными функциями, которые классифицируют символы типа `char`. Дополнительные сведения см. в подразделе `Remarks` раздела [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](global-state.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>См. также раздел

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
