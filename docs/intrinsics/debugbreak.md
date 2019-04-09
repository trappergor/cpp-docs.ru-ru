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
ms.openlocfilehash: b52c34014402a235e03c45f82dcd1e5c542e4919
ms.sourcegitcommit: c7f90df497e6261764893f9cc04b5d1f1bf0b64b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/05/2019
ms.locfileid: "59023104"
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
|`__debugbreak`|x86, ARM, x64|\<intrin.h>|

## <a name="remarks"></a>Примечания

`__debugbreak` Компилятора встроенные, аналогичную [DebugBreak](https://msdn.microsoft.com/library/windows/desktop/ms679297.aspx), — это переносимые Win32 способ создания точки останова.

> [!NOTE]
>  При компиляции с параметром **/CLR**, функция, содержащая `__debugbreak` будет компилироваться в MSIL. `asm int 3` вызывает функцию для компиляции в машинный код. Дополнительные сведения см. в разделе [__asm](../assembler/inline/asm.md).

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

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные объекты компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)