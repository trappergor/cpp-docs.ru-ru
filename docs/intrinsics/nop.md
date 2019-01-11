---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: b0033b0e3a62a16c2856b0e25daeebdb5df0c81f
ms.sourcegitcommit: a1fad0a266b20b313364a74b16c9ac45d089b1e9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 01/11/2019
ms.locfileid: "54220391"
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
|`__nop`|x86, ARM, x64, ARM64|

**Файл заголовка** \<intrin.h >

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="remarks"></a>Примечания

Функция `__nop` эквивалентна инструкции компьютера `NOP` . Дополнительные сведения о x86 и x64 поиска для документа, «руководство разработчика архитектуры Intel программного обеспечения, том 2: Справочник по набору инструкций,» в [корпорации Intel](https://software.intel.com/articles/intel-sdm) сайта.

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[__noop](../intrinsics/noop.md)
