---
title: Встроенные функции _InterlockedExchangePointer
ms.date: 12/17/2018
f1_keywords:
- _InterlockedExchangePointer_cpp
- _InterlockedExchangePointer_rel
- _InterlockedExchangePointer_nf
- _InterlockedExchangePointer_HLERelease
- _InterlockedExchangePointer_acq
- _InterlockedExchangePointer
- _InterlockedExchangePointer_acq_cpp
- _InterlockedExchangePointer_HLEAcquire
helpviewer_keywords:
- _InterlockedExchangePointer_rel intrinsic
- _InterlockedExchangePointer_HLERelease intrinsic
- _InterlockedExchangePointer intrinsic
- _InterlockedExchangePointer_nf intrinsic
- _InterlockedExchangePointer_acq intrinsic
- _InterlockedExchangePointer_HLEAcquire intrinsic
- InterlockedExchangePointer_acq intrinsic
- InterlockedExchangePointer intrinsic
ms.assetid: 0eaca0b0-d79e-406b-892d-b3b462c50bbb
ms.openlocfilehash: 021c754436d6abe877e6b7dd372ba235869d8975
ms.sourcegitcommit: ff3cbe4235b6c316edcc7677f79f70c3e784ad76
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/19/2018
ms.locfileid: "53627497"
---
# <a name="interlockedexchangepointer-intrinsic-functions"></a>Встроенные функции _InterlockedExchangePointer

**Блок, относящийся только к системам Microsoft**

Выполняет элементарную операцию обмена, которая копирует адрес, переданный в качестве второго аргумента в первый и возвращает исходный адрес первого.

## <a name="syntax"></a>Синтаксис

```
void * _InterlockedExchangePointer(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_acq(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_rel(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_nf(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLEAcquire(
   void * volatile * Target,
   void * Value
);
void * _InterlockedExchangePointer_HLERelease(
   void * volatile * Target,
   void * Value
);
```

#### <a name="parameters"></a>Параметры

*Целевой объект*<br/>
[in, out] Указатель на указатель на значение для обмена. Эта функция устанавливает значение `Value` и возвращает предыдущее значение.

*Значение*<br/>
[in] Значение для обмена со значением, на которые указывают `Target`.

## <a name="return-value"></a>Возвращаемое значение

Функция возвращает начальное значение,  на которое указывает `Target`.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_InterlockedExchangePointer`|x86, ARM, x64|\<Intrin.h >|
|`_InterlockedExchangePointer_acq`, `_InterlockedExchangePointer_rel`, `_InterlockedExchangePointer_nf`|ARM|\<Intrin.h >|
|`_InterlockedExchangePointer_HLEAcquire`, `_InterlockedExchangePointer_HLERelease`|x64 с поддержкой hle|\<immintrin.h >|

В архитектуре x86, `_InterlockedExchangePointer` есть макрос, вызывающий `_InterlockedExchange`.

## <a name="remarks"></a>Примечания

Для 64-разрядной системы параметры 64-разрядные и должны быть выровнены по  64-разрядным границам; в противном случае функция завершается с ошибкой. Для 32-разрядной системы параметры 32-разрядные и должны быть выровнены по 32-разрядням границам. Дополнительные сведения см. в разделе [выровнять](../cpp/align-cpp.md).

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенная функция с суффиксом `_nf` («без границ») не действует как ограничитель памяти.

На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision (HLE), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования. Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.

Эти процедуры доступны только как встроенные объекты.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)