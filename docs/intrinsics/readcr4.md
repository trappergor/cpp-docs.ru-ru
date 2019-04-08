---
title: __readcr4
ms.date: 11/04/2016
f1_keywords:
- __readcr4
helpviewer_keywords:
- __readcr4 intrinsic
ms.assetid: b841a27b-fe0d-4ee9-b76b-f91d3eb061fa
ms.openlocfilehash: b67016846768be778881c02b395c8d6f3af1ef3f
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59037228"
---
# <a name="readcr4"></a>__readcr4

**Блок, относящийся только к системам Microsoft**

Считывает регистр CR4 и возвращает его значение.

## <a name="syntax"></a>Синтаксис

```
unsigned __int64 __readcr4(void);
```

## <a name="return-value"></a>Возвращаемое значение

Значение в регистре CR4.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readcr4`|x86, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция доступна только в режиме ядра и процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)