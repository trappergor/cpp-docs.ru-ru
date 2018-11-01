---
title: _enable
ms.date: 11/04/2016
f1_keywords:
- _enable
- _enable_cpp
helpviewer_keywords:
- enable intrinsic
- _enable intrinsic
- ssm instruction
ms.assetid: 8bee669b-6bd8-4e25-9383-bb7d57295b4d
ms.openlocfilehash: 1d129db17b489972555efb0b5df2de52e01fa649
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50631255"
---
# <a name="enable"></a>_enable

**Блок, относящийся только к системам Microsoft**

Позволяет прерывания.

## <a name="syntax"></a>Синтаксис

```
void _enable(void);
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_enable`|x86, ARM, x64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

`_enable` Указывает процессору установить флаг прерывания. На платформе x86 систем, эта функция создает инструкцию установить флаг прерывания (`sti`) .

Эта функция доступна только в режиме ядра. При использовании в пользовательском режиме, исключение привилегированной инструкции отбрасывается.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)