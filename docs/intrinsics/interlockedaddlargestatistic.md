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
ms.openlocfilehash: 6f9d599a8d7668c6c8a37846275e8338002589d1
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59033418"
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

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Конфликты с компилятором x86](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)