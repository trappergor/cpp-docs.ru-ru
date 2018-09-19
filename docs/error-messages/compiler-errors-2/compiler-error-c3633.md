---
title: Ошибка компилятора C3633 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C3633
dev_langs:
- C++
helpviewer_keywords:
- C3633
ms.assetid: 7d65babf-2191-4d67-a69f-f5c4c2ddf946
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: aaa4712fb571d56166204655aff95153ac328ce6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46078274"
---
# <a name="compiler-error-c3633"></a>Ошибка компилятора C3633

Невозможно определить «член» в качестве члена управляемого «тип»

Члены данных среды CLR ссылочного класса не может иметь тип POD C++.  Можно создать только собственный тип POD в типе CLR.  Например тип POD не может содержать конструктор копии или оператор присваивания.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки C3633.

```
// C3633.cpp
// compile with: /clr /c
#pragma warning( disable : 4368 )

class A1 {
public:
   A1() { II = 0; }
   int II;
};

ref class B {
public:
   A1 a1;   // C3633
   A1 * a2;   // OK
   B() : a2( new A1 ) {}
    ~B() { delete a2; }
};
```
