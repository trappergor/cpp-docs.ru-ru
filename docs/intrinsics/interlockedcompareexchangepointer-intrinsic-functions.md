---
title: Встроенные функции _InterlockedCompareExchangePointer
ms.date: 11/04/2016
f1_keywords:
- _InterlockedCompareExchangePointer_HLERelease
- _InterlockedCompareExchangePointer_rel
- _InterlockedCompareExchangePointer_acq_cpp
- _InterlockedCompareExchangePointer
- _InterlockedCompareExchangePointer_cpp
- _InterlockedCompareExchangePointer_np
- _InterlockedCompareExchangePointer_rel_cpp
- _InterlockedCompareExchangePointer_HLEAcquire
- _InterlockedCompareExchangePointer_acq
- _InterlockedCompareExchangePointer_nf
helpviewer_keywords:
- InterlockedCompareExchangePointer_acq intrinsic
- _InterlockedCompareExchangePointer_rel intrinsic
- _InterlockedCompareExchangePointer_acq intrinsic
- InterlockedCompareExchangePointer_rel intrinsic
- InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_HLERelease intrinsic
- _InterlockedCompareExchangePointer_HLEAcquire intrinsic
- _InterlockedCompareExchangePointer intrinsic
- _InterlockedCompareExchangePointer_nf intrinsic
- _InterlockedCompareExchangePointer_np intrinsic
ms.assetid: 97fde59d-2bf9-42aa-a0fe-a5b6befdd44b
ms.openlocfilehash: 2db18c73f7765454d29e2dfdbd9408f62c51d32a
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59024820"
---
# <a name="interlockedcompareexchangepointer-intrinsic-functions"></a>Встроенные функции _InterlockedCompareExchangePointer

**Блок, относящийся только к системам Microsoft**

Выполняет атомарную операцию, которая сохраняет адрес `Exchange` в адресе `Destination`, если адреса `Comparand` и `Destination` равны.

## <a name="syntax"></a>Синтаксис

```
void * _InterlockedCompareExchangePointer (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_acq (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLEAcquire (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_HLERelease (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_nf (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
void * _InterlockedCompareExchangePointer_np (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
long _InterlockedCompareExchangePointer_rel (
   void * volatile * Destination,
   void * Exchange,
   void * Comparand
);
```

#### <a name="parameters"></a>Параметры

*Назначение*<br/>
[in, out] Указатель на указатель на значение назначения. Знак игнорируется

*Exchange*<br/>
[in] Указатель обмена. Знак игнорируется

*Сравниваемый операнд*<br/>
[in] Указатель для сравнения с местом назначения. Знак игнорируется

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение является начальным значением места назначения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_InterlockedCompareExchangePointer`|x86, ARM, x64|\<intrin.h>|
|`_InterlockedCompareExchangePointer_acq`значение `_InterlockedCompareExchangePointer_nf`значение `_InterlockedCompareExchangePointer_rel`|ARM|\<iiintrin.h>|
|`_InterlockedCompareExchangePointer_HLEAcquire`, `_InterlockedCompareExchangePointer_HLERelease`|x86, x64|\<immintrin.h>|

## <a name="remarks"></a>Примечания

`_InterlockedCompareExchangePointer` выполняет атомарное сравнение адреса `Destination` адрес с `Comparand` адресом. Если адрес `Destination` равен адресу `Comparand`, адрес `Exchange` сохраняется в адресе, указанном в `Destination`. В противном случае операция не выполняется.

`_InterlockedCompareExchangePointer` предоставляет встроенную поддержку компилятора для пакета SDK Windows Win32 [_InterlockedCompareExchangePointer](https://msdn.microsoft.com/library/ff547863.aspx) функции.

Пример использования `_InterlockedCompareExchangePointer`, см. в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенные функции ARM с суффиксом `_nf` («без границ») не действуют как барьер памяти.

Встроенные функции с суффиксом `_np` («нет упреждающей выборки") запрещают возможную вставку компилятором операции упреждающей выборки.

На платформах Intel ®, поддерживающих инструкции Hardware Lock Elision (HLE), встроенные функции с суффиксами `_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования. Если эти встроенные функции вызываются на платформах, не поддерживающих HLE, подсказка игнорируется.

Эти процедуры доступны только как встроенные объекты.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)