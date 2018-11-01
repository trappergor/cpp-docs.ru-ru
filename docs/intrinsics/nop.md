---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 25ba27485990ceaae77e1827f0c74680914e2f40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50651728"
---
# <a name="nop"></a>__nop

**Блок, относящийся только к системам Microsoft**

Создает специфические для платформы машинный код, который не выполняет никаких действий.

## <a name="syntax"></a>Синтаксис

```
void __nop();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__nop`|x86, x64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="remarks"></a>Примечания

Функция `__nop` эквивалентна инструкции компьютера `NOP` . Дополнительные сведения см. в документе «Руководство разработчика архитектуры Intel программного обеспечения, том 2: ссылка на набор инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)