---
title: __nop
ms.date: 11/04/2016
f1_keywords:
- __nop
helpviewer_keywords:
- nop instruction
- __nop intrinsic
ms.assetid: 7a2a938b-87e0-476d-a348-03ea7635b6b9
ms.openlocfilehash: 1e76110c1ef0c4b98c295578189eedc99d76eeb9
ms.sourcegitcommit: 72583d30170d6ef29ea5c6848dc00169f2c909aa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/18/2019
ms.locfileid: "59038254"
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
