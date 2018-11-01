---
title: Ошибка компилятора C2384
ms.date: 11/04/2016
f1_keywords:
- C2384
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
ms.openlocfilehash: 1909fb999dd0f60224029b726f773c11fa69ee40
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50460324"
---
# <a name="compiler-error-c2384"></a>Ошибка компилятора C2384

member: невозможно применить __declspec(thread) к члену управляемого класса или класса WinRT

[Поток](../../cpp/thread.md) `__declspec` модификатор нельзя применять к членам управляемого класса или класса среды выполнения Windows.

Локальное хранилище статического потока в управляемом коде может использоваться только для статически загружаемых библиотек DLL (библиотека загружается статически при запуске процесса). Среда выполнения Windows не поддерживает локальное хранилище потока.

Следующая строка вызывает ошибку C2384. Также показано, как устранить ее в коде C++/CLI:

```
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