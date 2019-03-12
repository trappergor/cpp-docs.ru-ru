---
title: _CIfmod
ms.date: 11/04/2016
apiname:
- _CIfmod
apilocation:
- msvcrt.dll
- msvcr110_clr0400.dll
- msvcr100.dll
- msvcr80.dll
- msvcr90.dll
- msvcr120.dll
- msvcr110.dll
- api-ms-win-crt-math-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _CIfmod
- CIfmod
helpviewer_keywords:
- CIfmod intrinsic
- _CIfmod intrinsic
ms.assetid: 7c050653-7ec6-4810-b3a7-7a0057ea65ed
ms.openlocfilehash: b3f667c24a4b02a23d045a5061b41ac4acc4095b
ms.sourcegitcommit: dedd4c3cb28adec3793329018b9163ffddf890a4
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/11/2019
ms.locfileid: "57746842"
---
# <a name="cifmod"></a>_CIfmod

Вычисляет остаток с плавающей запятой от двух верхних значений в стеке.

## <a name="syntax"></a>Синтаксис

```
void __cdecl _CIfmod();
```

## <a name="remarks"></a>Примечания

Эта версия функции `fmod` включает специальные соглашения о вызовах, распознаваемые компилятором. Это ускоряет выполнение, поскольку исключает создание копий и помогает распределять регистры.

Полученное значение помещается в верхнюю часть стека.

## <a name="requirements"></a>Требования

**Платформа:** x86

## <a name="see-also"></a>См. также

[Алфавитный указатель функций](../c-runtime-library/reference/crt-alphabetical-function-reference.md)<br/>
[fmod, fmodf](../c-runtime-library/reference/fmod-fmodf.md)
