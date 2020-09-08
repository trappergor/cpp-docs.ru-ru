---
title: Встроенные функции _InterlockedIncrement
description: Встроенные функции компилятора Microsoft C/C++ для добавочного захвата.
ms.date: 09/03/2020
f1_keywords:
- _InterlockedIncrement_acq
- _InterlockedIncrement16_rel_cpp
- _InterlockedIncrement16_cpp
- _InterlockedIncrement64_rel
- _InterlockedIncrement_rel
- _InterlockedIncrement64_nf
- _InterlockedIncrement16_acq_cpp
- _InterlockedIncrement_rel_cpp
- _InterlockedIncrement64
- _InterlockedIncrement64_rel_cpp
- _InterlockedIncrement16_nf
- _InterlockedIncrement16_rel
- _InterlockedIncrement16_acq
- _InterlockedIncrement_nf
- _InterlockedIncrement_acq_cpp
- _InterlockedIncrement64_cpp
- _InterlockedIncrement64_acq_cpp
- _InterlockedIncrement
- _InterlockedIncrement_cpp
- _InterlockedIncrement64_acq
- _InterlockedIncrement16
helpviewer_keywords:
- _InterlockedIncrement64_rel intrinsic
- _InterlockedIncrement16_rel intrinsic
- InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16 intrinsic
- _InterlockedIncrement16_acq intrinsic
- _InterlockedIncrement_nf intrinsic
- _InterlockedIncrement_rel intrinsic
- _InterlockedIncrement64_nf intrinsic
- InterlockedIncrement_rel intrinsic
- InterlockedIncrement_acq intrinsic
- _InterlockedIncrement64_acq intrinsic
- _InterlockedIncrement16_nf intrinsic
- _InterlockedIncrement intrinsic
- _InterlockedIncrement64 intrinsic
- InterlockedIncrement64_rel intrinsic
- InterlockedIncrement64 intrinsic
- InterlockedIncrement16 intrinsic
- _InterlockedIncrement_acq intrinsic
- InterlockedIncrement intrinsic
ms.assetid: 37700615-f372-438b-bcef-d76e11839482
ms.openlocfilehash: 2148ae31f3eb03e398372db3bf15fc64e4857dd1
ms.sourcegitcommit: 4ed2d68634eb2fb77e18110a2d26bc0008be369c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/08/2020
ms.locfileid: "89556325"
---
# <a name="_interlockedincrement-intrinsic-functions"></a>`_InterlockedIncrement` встроенные функции

Предоставьте встроенную поддержку компилятора для функции Win32 Windows SDK [интерлоккединкремент](/windows/win32/api/winnt/nf-winnt-interlockedincrement) . `_InterlockedIncrement`Встроенные функции относятся **только к Microsoft**.

## <a name="syntax"></a>Синтаксис

```C
long _InterlockedIncrement(
   long volatile * lpAddend
);
long _InterlockedIncrement_acq(
   long volatile * lpAddend
);
long _InterlockedIncrement_rel(
   long volatile * lpAddend
);
long _InterlockedIncrement_nf(
   long volatile * lpAddend
);
short _InterlockedIncrement16(
   short volatile * lpAddend
);
short _InterlockedIncrement16_acq(
   short volatile * lpAddend
);
short _InterlockedIncrement16_rel(
   short volatile * lpAddend
);
short _InterlockedIncrement16_nf (
   short volatile * lpAddend
);
__int64 _InterlockedIncrement64(
   __int64 volatile * lpAddend
);
__int64 _InterlockedIncrement64_acq(
   __int64 volatile * lpAddend
);
__int64 _InterlockedIncrement64_rel(
   __int64 volatile * lpAddend
);
__int64 _InterlockedIncrement64_nf(
   __int64 volatile * lpAddend
);
```

### <a name="parameters"></a>Параметры

*лпадденд*\
[вход, выход] Указатель на переменную, которая должна быть увеличена.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, полученное после увеличения.

## <a name="requirements"></a>Требования

|Intrinsic|Architecture|Header|
|---------------|------------------|------------|
|`_InterlockedIncrement`, `_InterlockedIncrement16`|x86, ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedIncrement64`|ARM, x64, ARM64|\<intrin.h>|
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Примечания

Существуют несколько вариантов `_InterlockedIncrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.

Функция `_InterlockedIncrement` работает с 32-разрядными целыми значениями, `_InterlockedIncrement16`работает с 16-разрядными целыми значениями и `_InterlockedIncrement64`работает с 64-разрядными целыми значениями.

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенная функция с `_nf` суффиксом ("без ограждения") не выступает в качестве барьера памяти.

Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не-x86. Дополнительные сведения см. в разделе [выровняйте](../cpp/align-cpp.md).

Функция Win32 объявляется в `Wdm.h` или `Ntddk.h`.

Эти процедуры доступны только как встроенные объекты.

## <a name="example"></a>Пример

Пример использования см `_InterlockedIncrement` . в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

## <a name="see-also"></a>Дополнительно

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Словами](../cpp/keywords-cpp.md)\
[Конфликтует с компилятором x86](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
