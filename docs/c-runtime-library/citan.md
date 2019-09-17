---
title: _CItan
ms.date: 04/11/2018
api_name:
- _CItan
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-math-l1-1-0.dll
api_type:
- DLLExport
topic_type:
- apiref
f1_keywords:
- _CItan
- CItan
helpviewer_keywords:
- CItan intrinsic
- _CItan intrinsic
ms.assetid: d1ea3113-50a2-45a6-b6bc-680fcdcc0928
ms.openlocfilehash: e509d785648148e51004950076147b69c2db18ec
ms.sourcegitcommit: f19474151276d47da77cdfd20df53128fdcc3ea7
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/12/2019
ms.locfileid: "70940465"
---
# <a name="_citan"></a>_CItan

Вычисляет тангенс верхнего значения в стеке с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Примечания

Эта версия функции [tan](../c-runtime-library/reference/tan-tanf-tanl.md) включает специальные соглашения о вызовах, распознаваемые компилятором. Она ускоряет выполнение, так как исключает создание копий и помогает распределять регистры.

Полученное значение помещается в верхнюю часть стека с плавающей запятой.

## <a name="requirements"></a>Требования

**Платформа:** x86

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
