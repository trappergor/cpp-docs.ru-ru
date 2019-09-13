---
title: Встроенные функции _InterlockedIncrement
ms.date: 09/02/2019
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
ms.openlocfilehash: 4dd9ae9ba5454b0afefa332689d94fa3619a07a6
ms.sourcegitcommit: 6e1c1822e7bcf3d2ef23eb8fac6465f88743facf
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/03/2019
ms.locfileid: "70221986"
---
# <a name="_interlockedincrement-intrinsic-functions"></a>Встроенные функции _InterlockedIncrement

**Блок, относящийся только к системам Microsoft**

Предоставьте встроенную поддержку компилятора для функции Win32 Windows SDK [интерлоккединкремент](/windows/win32/api/winnt/nf-winnt-interlockedincrement) .

## <a name="syntax"></a>Синтаксис

```C
long _InterlockedIncrement(
   long * lpAddend
);
long _InterlockedIncrement_acq(
   long * lpAddend
);
long _InterlockedIncrement_rel(
   long * lpAddend
);
long _InterlockedIncrement_nf(
   long * lpAddend
);
short _InterlockedIncrement16(
   short * lpAddend
);
short _InterlockedIncrement16_acq(
   short * lpAddend
);
short _InterlockedIncrement16_rel(
   short * lpAddend
);
short _InterlockedIncrement16_nf (
   short * lpAddend
);
__int64 _InterlockedIncrement64(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_acq(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_rel(
   __int64 * lpAddend
);
__int64 _InterlockedIncrement64_nf(
   __int64 * lpAddend
);
```

### <a name="parameters"></a>Параметры

*лпадденд*\
[вход, выход] Указатель на переменную, которая должна быть увеличена.

## <a name="return-value"></a>Возвращаемое значение

Возвращаемое значение, полученное после увеличения.

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`_InterlockedIncrement`, `_InterlockedIncrement16`|x86, ARM, x64, ARM64|\<> Intrin. h|
|`_InterlockedIncrement64`|ARM, x64, ARM64|\<> Intrin. h|
|`_InterlockedIncrement_acq`, `_InterlockedIncrement_rel`, `_InterlockedIncrement_nf`, `_InterlockedIncrement16_acq`, `_InterlockedIncrement16_rel`, `_InterlockedIncrement16_nf`, `_InterlockedIncrement64_acq`, `_InterlockedIncrement64_rel`, `_InterlockedIncrement64_nf`|ARM, ARM64|\<> Intrin. h|

## <a name="remarks"></a>Примечания

Существуют несколько вариантов `_InterlockedIncrement`, они различаются в зависимости от типов данных, которые включают, и от того, используется ли семантика получения или освобождения конкретного процессора.

Функция `_InterlockedIncrement` работает с 32-разрядными целыми значениями, _InterlockedDecrement16`_InterlockedIncrement16`работает с 16-разрядными целыми значениями и _InterlockedDecrement64`_InterlockedIncrement64`работает с 64-разрядными целыми значениями.

На платформах ARM используйте встроенные функции с суффиксами `_acq` и `_rel`, если нужно получить и освободить семантику, например в начале и конце критической секции. Встроенная функция с `_nf` суффиксом ("без ограждения") не выступает в качестве барьера памяти.

Переменная, на который указывает параметр `lpAddend`, должна быть выровнена по границе 32 разрядов; в противном случае эта функция не выполняется на многопроцессорных системах x86 и любой системе не-x86. Дополнительные сведения см. в разделе [выровняйте](../cpp/align-cpp.md).

Функция Win32 объявляется в `Wdm.h` или `Ntddk.h`.

Эти процедуры доступны только как встроенные объекты.

## <a name="example"></a>Пример

Пример использования `_InterlockedIncrement`см. в разделе [_InterlockedDecrement](../intrinsics/interlockeddecrement-intrinsic-functions.md).

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные функции компилятора](../intrinsics/compiler-intrinsics.md)\
[Ключевые слова](../cpp/keywords-cpp.md)\
[Конфликты с 32-разрядным (x86) компилятором](../build/x64-software-conventions.md#conflicts-with-the-x86-compiler)
