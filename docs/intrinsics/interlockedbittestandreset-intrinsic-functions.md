---
title: встроенные функции _interlockedbittestandreset
ms.date: 11/04/2016
f1_keywords:
- _interlockedbittestandreset_rel
- _interlockedbittestandreset64
- _interlockedbittestandreset64_HLERelease
- _interlockedbittestandreset_HLERelease
- _interlockedbittestandreset_HLEAcquire
- _interlockedbittestandreset_acq
- _interlockedbittestandreset_cpp
- _interlockedbittestandreset_nf
- _interlockedbittestandreset64_cpp
- _interlockedbittestandreset64_HLEAcquire
- _interlockedbittestandreset
helpviewer_keywords:
- lock_btr instruction
- _interlockedbittestandreset64 intrinsic
- _interlockedbittestandreset intrinsic
ms.assetid: 9bbb1442-f2e9-4dc2-b0da-97f3de3493b9
ms.openlocfilehash: dc85b1a1bb76575f63d7c43bead08a6e850d026f
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50605404"
---
# <a name="interlockedbittestandreset-intrinsic-functions"></a>встроенные функции _interlockedbittestandreset

**Блок, относящийся только к системам Microsoft**

Создает инструкцию, которая устанавливает разряд `b` адреса `a`  в нулевое значение и возвращает исходное значение.

## <a name="syntax"></a>Синтаксис

```
unsigned char _interlockedbittestandreset(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_acq(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLEAcquire(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_HLERelease(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_nf(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset_rel(
   long *a,
   long b
);
unsigned char _interlockedbittestandreset64(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLEAcquire(
   __int64 *a,
   __int64 b
);
unsigned char _interlockedbittestandreset64_HLERelease(
   __int64 *a,
   __int64 b
);
```

#### <a name="parameters"></a>Параметры

*a*<br/>
[in] Указатель памяти для проверки.

*b*<br/>
[in] Позиция разряда для тестирования.

## <a name="return-value"></a>Возвращаемое значение

Исходное значение разряда в позиции, указанной параметром `b`.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_interlockedbittestandreset`|x86, ARM, x64|\<Intrin.h >|
|`_interlockedbittestandreset_acq`, `_interlockedbittestandreset_nf`, `_interlockedbittestandreset_rel`|ARM|\<Intrin.h >|
|`_interlockedbittestandreset_HLEAcquire`, `_interlockedbittestandreset_HLERelease`|x86, x64|\<immintrin.h >|
|`_interlockedbittestandreset64`|X64|\<Intrin.h >|
|`_interlockedbittestandreset64_HLEAcquire`, `_interlockedbittestandreset64_HLERelease`|X64|\<immintrin.h >|

## <a name="remarks"></a>Примечания

На процессорах x86 и x64, эти встроенные функции используют `lock btr` инструкции, которая считывает и задает нулевое значение указанного разряда в атомарной операции.

На процессорах ARM используются встроенные функции с суффиксами `_acq` и `_rel` для получения и освобождения семантики, например, в начале и конце критической секции. Встроенные функции ARM с суффиксом `_nf` («без границ») не действуют как барьер памяти.

Для процессоров Intel, поддерживающих инструкции Hardware Lock Elision (HLE), встроенные функции с суффиксами`_HLEAcquire` и `_HLERelease` включают подсказку процессору, как можно повысить производительность, устраняя шаг записи с блокировкой оборудования. Если эти встроенные функции вызываются на процессорах, не поддерживающих HLE, подсказка игнорируется.

Эти процедуры доступны только как встроенные объекты.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Конфликты с 32-разрядным (x86) компилятором](../build/conflicts-with-the-x86-compiler.md)