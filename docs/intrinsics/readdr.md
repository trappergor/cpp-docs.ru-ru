---
title: __readdr
ms.date: 09/02/2019
f1_keywords:
- __readdr
helpviewer_keywords:
- __readdr intrinsic
ms.assetid: 061b05da-c85e-4052-b392-106f14bb84f1
ms.openlocfilehash: 646330ca92af08903485fd4583eb2c217fe3e023
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70216676"
---
# <a name="__readdr"></a>__readdr

Считывает значение указанного регистра отладки.

## <a name="syntax"></a>Синтаксис

```C
unsigned         __readdr(unsigned int DebugRegister); /* x86 */
unsigned __int64 __readdr(unsigned int DebugRegister); /* x64 */
```

### <a name="parameters"></a>Параметры

*дебугрегистер*\
окне Константа от 0 до 7, определяющая регистр отладки.

## <a name="return-value"></a>Возвращаемое значение

Значение указанного регистра отладки.

## <a name="remarks"></a>Примечания

Эти встроенные функции доступны только в режиме ядра, а подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__readdr`|x86, x64|

**Заголовочный файл** \<> Intrin. h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readeflags](../intrinsics/readeflags.md)
