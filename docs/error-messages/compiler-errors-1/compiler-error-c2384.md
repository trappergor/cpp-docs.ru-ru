---
title: Ошибка компилятора C2384 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2384
dev_langs:
- C++
helpviewer_keywords:
- C2384
ms.assetid: 8145f7ad-31b1-406d-ac43-0d557feab635
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: f3aa9ec8a6a94f53123c443a1149df7cdbc95c83
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46020463"
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