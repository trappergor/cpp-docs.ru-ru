---
title: _disable | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- _disable_cpp
- _disable
dev_langs:
- C++
helpviewer_keywords:
- _disable intrinsic
- rsm instruction
- disable intrinsic
ms.assetid: 52da3df9-815c-4524-9839-6d1742cff5c6
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: e2e0eb09934847c2f7b67c9e4961b02d31c68df2
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46382418"
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