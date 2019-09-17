---
title: __pctype_func
ms.date: 11/04/2016
api_name:
- __pctype_func
api_location:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr120.dll
- msvcr90.dll
- msvcr100.dll
- msvcr80.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- __pctype_func
helpviewer_keywords:
- __pctype_func
ms.assetid: d52b8add-d07d-4516-a22f-e836cde0c57f
ms.openlocfilehash: f5dae74dd601df1dc737293a181eca60f5cd23f8
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70944040"
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

## <a name="remarks"></a>Примечания

Сведения в таблице классификации символов предназначены только для внутреннего пользования и используются различными функциями, которые классифицируют символы типа `char`. Дополнительные сведения см. в подразделе `Remarks` раздела [_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md).

## <a name="requirements"></a>Требования

|Подпрограмма|Обязательный заголовок|
|-------------|---------------------|
|__pctype_func|ctype.h|

## <a name="see-also"></a>См. также

[_pctype, _pwctype, _wctype, _mbctype, _mbcasemap](../c-runtime-library/pctype-pwctype-wctype-mbctype-mbcasemap.md)
