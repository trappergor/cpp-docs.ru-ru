---
title: _CIatan2
ms.date: 11/04/2016
apiname:
- _CIatan2
apilocation:
- msvcr80.dll
- msvcrt.dll
- msvcr120.dll
- msvcr110_clr0400.dll
- msvcr110.dll
- msvcr100.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- CIatan2
- _CIatan2
helpviewer_keywords:
- _CIatan2 intrinsic
- CIatan2 intrinsic
ms.assetid: 31f8cc78-b79f-4576-b73b-8add18e08680
ms.openlocfilehash: a09bc8af5ab6ef6d99efea8448098d1a2f03d580
ms.sourcegitcommit: e98671a4f741b69d6277da02e6b4c9b1fd3c0ae5
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/04/2019
ms.locfileid: "55703263"
---
# <a name="ciatan2"></a>_CIatan2

Вычисляет арктангенс *x* / *y*, где *x* и *y* представляют собой значения из верхней части стека.

## <a name="syntax"></a>Синтаксис

```
void __cdecl _CIatan2();
```

## <a name="remarks"></a>Примечания

Эта версия функции `atan2` включает специальные соглашения о вызовах, распознаваемые компилятором. Это ускоряет выполнение, поскольку исключает создание копий и помогает распределять регистры.

Полученное значение помещается в верхнюю часть стека.

## <a name="requirements"></a>Требования

**Платформа:** x86

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[atan, atanf, atanl, atan2, atan2f, atan2l](../c-runtime-library/reference/atan-atanf-atanl-atan2-atan2f-atan2l.md)