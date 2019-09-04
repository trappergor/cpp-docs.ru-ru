---
title: __readeflags
ms.date: 09/02/2019
f1_keywords:
- __readeflags
helpviewer_keywords:
- __readeflags intrinsic
ms.assetid: f9d2f4d8-c428-491f-b8de-04d0566b2b6b
ms.openlocfilehash: fe2365c2837b6c583810bb9fc908fe98486a2d38
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221228"
---
# <a name="__readeflags"></a>__readeflags

Считывает Регистр состояния программы и управления (ЕФЛАГС).

## <a name="syntax"></a>Синтаксис

```C
unsigned     int __readeflags(void); /* x86 */
unsigned __int64 __readeflags(void); /* x64 */
```

## <a name="return-value"></a>Возвращаемое значение

Значение регистра ЕФЛАГС. Возвращаемое значение — 32 бит на 32-разрядной платформе и 64 бит на 64-разрядной платформе.

## <a name="remarks"></a>Примечания

Эти подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readeflags`|x86, x64|

**Заголовочный файл** \<> Intrin. h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__writeeflags](../intrinsics/writeeflags.md)
