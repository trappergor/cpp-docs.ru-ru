---
title: Ошибка компилятора C3195
ms.date: 11/04/2016
f1_keywords:
- C3195
helpviewer_keywords:
- C3195
ms.assetid: 97e4f681-812b-49e8-ba57-24b7817e3cd8
ms.openlocfilehash: 4a54a9c629a1abaa4f1c5d15d06448e82cf25561
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62329105"
---
# <a name="compiler-error-c3195"></a>Ошибка компилятора C3195

operator: зарезервирован и не может использоваться как элемент ссылочного класса или типа значения. Операторы среды CLR или WinRT должны быть определены с помощью ключевого слова operator

Компилятор обнаружил определение оператора с использованием синтаксиса управляемых расширений для C++. Для операторов, необходимо использовать синтаксис C++.

В следующем примере показано возникновение ошибки C3195 и приводятся сведения по ее устранению.

```
// C3195.cpp
// compile with: /clr /LD
#using <mscorlib.dll>
value struct V {
   static V op_Addition(V v, int i);   // C3195
   static V operator +(V v, char c);   // OK for new C++ syntax
};
```