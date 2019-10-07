---
title: _CIpow
ms.date: 11/04/2016
api_name:
- _CIpow
api_location:
- msvcr100.dll
- msvcr110.dll
- msvcr120.dll
- msvcr80.dll
- msvcr110_clr0400.dll
- msvcrt.dll
- msvcr90.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- CIpow
- _CIpow
helpviewer_keywords:
- CIpow intrinsic
- _CIpow intrinsic
ms.assetid: 477aaf0c-ac58-4252-89dd-9f3e35d47536
ms.openlocfilehash: b32d7c550d465052f7c1dcd4a81baab803ec28f0
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940519"
---
# <a name="_cipow"></a>_CIpow

Вычисляет значение *x*, возведенное в степень *y*, исходя из верхних значений в стеке.

## <a name="syntax"></a>Синтаксис

```
void __cdecl _CIpow();
```

## <a name="remarks"></a>Примечания

Эта версия функции `pow` включает специальные соглашения о вызовах, распознаваемые компилятором. Это ускоряет выполнение, поскольку исключает создание копий и помогает распределять регистры.

Полученное значение помещается в верхнюю часть стека.

## <a name="requirements"></a>Требования

**Платформа:** x86

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[pow, powf, powl](../c-runtime-library/reference/pow-powf-powl.md)
