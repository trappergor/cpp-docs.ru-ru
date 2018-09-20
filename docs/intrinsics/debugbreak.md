---
title: __debugbreak | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
f1_keywords:
- __debugbreak_cpp
- __debugbreak
dev_langs:
- C++
helpviewer_keywords:
- breakpoints, __debugbreak intrinsic
- __debugbreak intrinsic
ms.assetid: 1d1e1c0c-891a-4613-ae4b-d790094ba830
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f2ba9322f4fe94c1c857b0494dc79b417e5d65d8
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46433903"
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
|`__debugbreak`|x86, ARM, x64|\<Intrin.h >|

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

Эта процедура доступна только как встроенная функция.

**Завершение блока, относящегося только к системам Майкрософт**

## <a name="see-also"></a>См. также

[Встроенные инструкции компилятора](../intrinsics/compiler-intrinsics.md)<br/>
[Ключевые слова](../cpp/keywords-cpp.md)