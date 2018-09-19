---
title: Ошибка компилятора C2793 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2793
dev_langs:
- C++
helpviewer_keywords:
- C2793
ms.assetid: ce35f4e8-c357-40ca-95c4-15ff001ad69d
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: d5b9f350a3d3845649c9423a412ed5286cb13723
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46026209"
---
# <a name="compiler-error-c2793"></a>Ошибка компилятора C2793

«токен»: непредвиденная лексема после "::", идентификатор или ключевое слово «operator» ожидается

Только токены, которые можно выполнить `__super::` идентификатор или ключевое слово `operator`.

Следующий пример приводит к возникновению ошибки C2793

```
// C2793.cpp
struct B {
   void mf();
};

struct D : B {
   void mf() {
      __super::(); // C2793
   }
};
```