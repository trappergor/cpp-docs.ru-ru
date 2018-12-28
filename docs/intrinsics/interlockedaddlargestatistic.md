---
title: _InterlockedAddLargeStatistic
ms.date: 11/04/2016
f1_keywords:
- _InterlockedAddLargeStatistic
- _InterlockedAddLargeStatistic_cpp
helpviewer_keywords:
- _InterlockedAddLargeStatistic intrinsic
- InterlockedAddLargeStatistic intrinsic
ms.assetid: 2802e74b-bcee-46e4-b562-894908d44409
ms.openlocfilehash: 88ada0a906b777ab8ac676ddfe0a5166e906999d
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627476"
---
# <a name="interlockedaddlargestatistic"></a>_InterlockedAddLargeStatistic

**Блок, относящийся только к системам Microsoft**

Выполняет блокируемое сложение, в котором первый операнд является 64-разрядное значение.

## <a name="syntax"></a>Синтаксис

```
long _InterlockedAddLargeStatistic(
   __int64 volatile * Addend,
   long Value
);
```

#### <a name="parameters"></a>Параметры

*Слагаемое*<br/>
[in, out] Указатель на первый операнд в операции добавления. Значение, на которое заменяется результатом сложения.

*Значение*<br/>
[in] Второй операнд; значение для первого операнда.

## <a name="return-value"></a>Возвращаемое значение

Значение второго операнда.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|
|---------------|------------------|
|`_InterlockedAddLargeStatistic`|x86|

**Файл заголовка** \<intrin.h >

## <a name="remarks"></a>Примечания

Эта встроенная функция не является атомарным, так как он реализован как два отдельных заблокированной инструкции. Atomic чтения 64-разрядной, выполняемое в другом потоке во время выполнения это внутренние может привести значение несогласованные выполняется чтение.

Эта функция действует как барьер чтения и записи. Дополнительные сведения см. в разделе [_ReadWriteBarrier](../intrinsics/readwritebarrier.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)