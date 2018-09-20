---
title: __faststorefence | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __faststorefence_cpp
- __faststorefence
dev_langs:
- C++
helpviewer_keywords:
- __faststorefence intrinsic
- sfence instruction
ms.assetid: 6c6eb973-3cf0-4306-b3af-cfde9b0210a5
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 5047dbb2023272ab03cc7d49f877f0fcc38a7b76
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402191"
---
# <a name="faststorefence"></a>__faststorefence

**Блок, относящийся только к системам Microsoft**

Гарантирует, что каждая предыдущая ссылка на память, включая ссылки как на память чтения, так и на память записи, являются глобально видимыми до создания последующей ссылки на память.

## <a name="syntax"></a>Синтаксис

```
void __faststorefence();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`__faststorefence`|X64|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Создает последовательность инструкций барьера полной памяти, которая гарантирует, что операции чтения и записи выдаются до того, как встроенные события становятся глобально видимыми перед тем, как продолжится выполнение. Эффект сравним со встроенной инструкцией `_mm_mfence` на всех платформах x64.

На платформе AMD64 этот процесс создает инструкцию, которая является барьером записи и позволяет работать быстрее, чем инструкция `sfence`. Для критичного по времени кода встроенную инструкцию вместо `_mm_sfence` следует использовать только на платформах AMD64. На платформах Intel x64 инструкция `_mm_sfence` будет выполняться быстрее.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)