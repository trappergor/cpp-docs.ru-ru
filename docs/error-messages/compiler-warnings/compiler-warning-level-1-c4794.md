---
title: Предупреждение компилятора (уровень 1) C4794
ms.date: 11/04/2016
f1_keywords:
- C4794
helpviewer_keywords:
- C4794
ms.assetid: badc9c36-fa1a-4fec-929b-7bfda7a7b79f
ms.openlocfilehash: 7d669280c0dc6a730a22480e602dac8cc6153449
ms.sourcegitcommit: 458dcc794e3841919c01a3a5ff6b9a3767f8861b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/13/2019
ms.locfileid: "74052369"
---
# <a name="compiler-warning-level-1-c4794"></a>Предупреждение компилятора (уровень 1) C4794

сегмент переменной из локальной памяти потока "переменная" изменен с "имя_раздела" на ".tls$"

Вы использовали [#pragma data_seg](../../preprocessor/data-seg.md) , чтобы поместить переменную tls в раздел, не начинающийся с ".tls$".

Раздел .tls$*x* раздел будет существовать в объектном файле, где определены переменные [__declspec(thread)](../../cpp/thread.md) . Раздел .tls в файле EXE или DLL будет получен из этих разделов.

## <a name="example"></a>Пример

В следующем примере возникает ошибка C4794.

```cpp
// C4794.cpp
// compile with: /W1 /c
#pragma data_seg(".someseg")
__declspec(thread) int i;   // C4794

// OK
#pragma data_seg(".tls$9")
__declspec(thread) int j;
```