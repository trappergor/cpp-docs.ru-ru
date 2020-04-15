---
title: _CItan
ms.date: 4/2/2020
api_name:
- _CItan
- _o__CItan
api_location:
- msvcr100.dll
- msvcr110_clr0400.dll
- msvcr80.dll
- msvcrt.dll
- msvcr110.dll
- msvcr90.dll
- msvcr120.dll
- api-ms-win-crt-math-l1-1-0.dll
- api-ms-win-crt-private-l1-1-0
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
ms.openlocfilehash: 8c6cc0a51d6ef2132172164306b84f73799da729
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81349366"
---
# <a name="_citan"></a>_CItan

Вычисляет тангенс верхнего значения в стеке с плавающей запятой.

## <a name="syntax"></a>Синтаксис

```C
void __cdecl _CItan();
```

## <a name="remarks"></a>Remarks

Эта версия функции [tan](../c-runtime-library/reference/tan-tanf-tanl.md) включает специальные соглашения о вызовах, распознаваемые компилятором. Она ускоряет выполнение, так как исключает создание копий и помогает распределять регистры.

Полученное значение помещается в верхнюю часть стека с плавающей запятой.

По умолчанию глобальное состояние этой функции приспозировано к приложению. Чтобы изменить это, [см. Глобальное состояние в CRT](global-state.md).

## <a name="requirements"></a>Требования

**Платформа:** x86

## <a name="see-also"></a>См. также раздел

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[tan, tanf, tanl](../c-runtime-library/reference/tan-tanf-tanl.md)<br/>
