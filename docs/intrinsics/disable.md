---
title: _disable
ms.date: 11/04/2016
f1_keywords:
- _disable_cpp
- _disable
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
ms.openlocfilehash: 64e7031ab578632322dfd5c73eb81e0750c1e0b5
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50587815"
---
# <a name="disable"></a>_disable

**Блок, относящийся только к системам Microsoft**

Отключение прерываний.

## <a name="syntax"></a>Синтаксис

```
void _disable(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_disable`|x86, ARM, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`_disable` Указывает процессору очистить флаг прерывания. На платформе x86 систем, эта функция создает инструкцию снятия флага прерывания (`cli`) .

Эта функция доступна только в режиме ядра. При использовании в пользовательском режиме, исключение привилегированной инструкции во время выполнения отбрасывается.

На платформах ARM эта процедура доступна только как встроенная.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)