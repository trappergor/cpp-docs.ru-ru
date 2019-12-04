---
title: Ошибка компилятора C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 2ce5c2f2540fbd2aca3509fa1dac55073a002abb
ms.sourcegitcommit: 16fa847794b60bf40c67d20f74751a67fccb602e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/03/2019
ms.locfileid: "74745269"
---
# <a name="compiler-error-c2384"></a>Ошибка компилятора C2384

member: невозможно применить __declspec(thread) к члену управляемого класса или класса WinRT

Модификатор [потока](../../cpp/thread.md) `__declspec` не может использоваться для члена управляемого или среда выполнения Windows класса.

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
