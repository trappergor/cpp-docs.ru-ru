---
title: Ошибка средств компоновщика LNK2020 | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- LNK2020
dev_langs:
- C++
helpviewer_keywords:
- LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 90088d311bac7ee4ce59797d5dcbe148a24963f6
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46034971"
---
# <a name="linker-tools-error-lnk2020"></a>Ошибка средств компоновщика LNK2020

неразрешенная лексема «лексема»

Аналогично неопределенной внешней ошибки, за исключением того, что ссылка разрешается через метаданные. В метаданных все функции и данные должны быть определены.

Чтобы разрешить:

- Определите отсутствующие функции или данные, или

- Включайте файл объекта или библиотеки, в которой отсутствует функция или данных уже определен.

## <a name="example"></a>Пример

Следующий пример приводит к возникновению ошибки LNK2020.

```
// LNK2020.cpp
// compile with: /clr /LD
ref struct A {
   A(int x);   // LNK2020
   static int f();   // LNK2020
};

// OK
ref struct B {
   B(int x) {}
   static int f() { return 0; }
};
```

## <a name="example"></a>Пример

LNK2020 может также возникнуть, если создать переменную типа управляемого типа шаблона, но не создается экземпляр типа.

Следующий пример приводит к возникновению ошибки LNK2020.

```
// LNK2020_b.cpp
// compile with: /clr

template <typename T>
ref struct Base {
   virtual void f1() {};
};

template <typename T>
ref struct Base2 {
   virtual void f1() {};
};

int main() {
   Base<int>^ p;   // LNK2020
   Base2<int>^ p2 = gcnew Base2<int>();   // OK
};
```