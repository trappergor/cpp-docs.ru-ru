---
title: __writedr
ms.date: 09/02/2019
f1_keywords:
- __writedr
helpviewer_keywords:
- __writedr intrinsic
ms.assetid: ac55c1ee-df2f-41d4-a429-6f369d2a934d
ms.openlocfilehash: 715ef7432d506c2758c9c3da913e9c0ebb24e13f
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70219227"
---
# <a name="__writedr"></a>__writedr

Записывает указанное значение в указанный регистр отладки.

## <a name="syntax"></a>Синтаксис

```C
void __writedr(unsigned DebugRegister, unsigned DebugValue); /* x86 */
void __writedr(unsigned DebugRegister, unsigned __int64 DebugValue); /* x64 */
```

### <a name="parameters"></a>Параметры

*дебугрегистер*\
окне Число от 0 до 7, идентифицирующее регистр отладки.

*дебугвалуе*\
окне Значение, записываемое в регистр отладки.

## <a name="remarks"></a>Примечания

Эти встроенные функции доступны только в режиме ядра, а подпрограммы доступны только в виде встроенных функций.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__writedr`|x86, x64|

**Заголовочный файл** \<> Intrin. h

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[__readdr](../intrinsics/readdr.md)
