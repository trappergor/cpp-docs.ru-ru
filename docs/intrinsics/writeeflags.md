---
title: __writeeflags
ms.date: 09/02/2019
f1_keywords:
- __writeeflags
helpviewer_keywords:
- __writeeflags intrinsics
ms.assetid: a62a522c-d7fa-4f10-a620-a3b32bdf3f17
ms.openlocfilehash: e43789d2fbed1bdc52665531c61c6c932a27f5ab
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219144"
---
# <a name="__writeeflags"></a>__writeeflags

Записывает указанное значение в Регистр состояния программы и контроль (ЕФЛАГС).

## <a name="syntax"></a>Синтаксис

```C
void __writeeflags(unsigned Value); /* x86 */
void __writeeflags(unsigned __int64 Value); /* x64 */
```

### <a name="parameters"></a>Параметры

*Значений*\
окне Значение, записываемое в ЕФЛАГС регистр. `Value` Параметр имеет длину 32 бит/с для 32-разрядной платформы и 64 разрядов для 64-разрядной платформы.

## <a name="remarks"></a>Примечания

Эти подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writeeflags`|x86, x64|

**Заголовочный файл** \<> Intrin. h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
