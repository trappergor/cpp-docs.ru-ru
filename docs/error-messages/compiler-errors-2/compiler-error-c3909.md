---
title: Ошибка компилятора C3909 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3909
dev_langs:
- C++
helpviewer_keywords:
- C3909
ms.assetid: 0a443132-e53f-42dc-a58b-f086da3e7bfd
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 7bb3526f537a2eceb006f6af9e9b0faba44bf9cf
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46058709"
---
# <a name="compiler-error-c3909"></a>Ошибка компилятора C3909

aWinRT или объявление управляемого события должно находиться в управляемом типе или типе WinRT

Событие среды выполнения Windows или управляемое событие было объявлено в собственном типе. Чтобы устранить эту ошибку, объявите события в типах среды выполнения Windows или управляемых типах.

Дополнительные сведения см. в разделе [событий](../../windows/event-cpp-component-extensions.md).

В следующем примере показано возникновение ошибки C3909 и приводятся сведения по ее устранению.

```
// C3909.cpp
// compile with: /clr /c
delegate void H();
class X {
   event H^ E;   // C3909 - use ref class X instead
};

ref class Y {
   static event H^ E {
      void add(H^) {}
      void remove( H^ h ) {}
      void raise( ) {}
   }
};
```