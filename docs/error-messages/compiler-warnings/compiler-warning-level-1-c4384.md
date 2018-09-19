---
title: Предупреждение компилятора (уровень 1) C4384 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C4384
dev_langs:
- C++
helpviewer_keywords:
- C4384
ms.assetid: fafa8eb2-cbfc-4edb-8b0f-511ff5d37ac0
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 54d913aac76f767728bbe7b4a31d4ea1c8bbd96d
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46027002"
---
# <a name="compiler-warning-level-1-c4384"></a>Предупреждение компилятора (уровень 1) C4384

\#Директива pragma «make_public» следует использовать только в глобальной области видимости

[Make_public](../../preprocessor/make-public.md) pragma был применен неправильно.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C4384.

```
// C4384.cpp
// compile with: /c /W1
namespace n {
   #pragma make_public(N::C)   // C4384
   namespace N {
      class C {};
   }
}
```