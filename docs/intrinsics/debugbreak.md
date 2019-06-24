---
title: __debugbreak
ms.date: 11/04/2016
f1_keywords:
- __debugbreak_cpp
- __debugbreak
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
ms.openlocfilehash: 97932dfe0e187a13b72ae5fe70d761224721c3ff
ms.sourcegitcommit: 1acb6755e11379026a96f63facac4d33f4dc47ae
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/21/2019
ms.locfileid: "67314257"
---
# <a name="debugbreak"></a>__debugbreak

**Блок, относящийся только к системам Microsoft**

Вызывает точку останова в коде, где пользователю будет предложено запустить отладчик.

## <a name="syntax"></a>Синтаксис

```
void __debugbreak();
```

## <a name="requirements"></a>Требования

|Встроенная функция|Архитектура|Header|
|---------------|------------------|------------|
|`__debugbreak`|x86, x 64, ARM, ARM64|\<intrin.h>|

## <a name="remarks"></a>Примечания

`__debugbreak` Компилятора встроенные, аналогичную [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), — это переносимые Win32 способ создания точки останова.

> [!NOTE]
>  При компиляции с параметром **/CLR**, функция, содержащая `__debugbreak` будет компилироваться в MSIL. При использовании `asm int 3` функция компилируется в машинный код. Дополнительные сведения см. в разделе [__asm](../assembler/inline/asm.md).

Пример:

```
main() {
   __debugbreak();
}
```

аналогично

```
main() {
   __asm {
      int 3
   }
}
```

на компьютере с архитектурой x86.

На ARM64 `__debugbreak` функция компилируется в инструкцию `brk #0xF000`.

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)
