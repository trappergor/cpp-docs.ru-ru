---
title: Ошибка компилятора C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 321ccd23bc273f5fa548f75fd44bc320bcf4c426
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87225518"
---
# <a name="compiler-error-c2384"></a>Ошибка компилятора C2384

member: невозможно применить __declspec(thread) к члену управляемого класса или класса WinRT

Модификатор [потока](../../cpp/thread.md) **`__declspec`** не может использоваться для члена управляемого или среда выполнения Windows класса.

Локальное хранилище статического потока в управляемом коде может использоваться только для статически загружаемых библиотек DLL (библиотека  загружается статически при запуске процесса). Среда выполнения Windows не поддерживает локальное хранилище потока.

Следующая строка вызывает ошибку C2384. Также показано, как устранить ее в коде C++/CLI:

```cpp
// C2384.cpp
// compile with: /clr /c
public ref class B {
public:
   __declspec( thread ) static int tls_i = 1;   // C2384

   // OK - declare with attribute instead
   [System::ThreadStaticAttribute]
   static int tls_j;
};
```
