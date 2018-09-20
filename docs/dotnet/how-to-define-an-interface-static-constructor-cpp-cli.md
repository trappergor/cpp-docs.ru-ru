---
title: 'Практическое: определение статического конструктора интерфейса (C + +/ CLI) | Документация Майкрософт'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- constructors [C++]
- static constructors, interface
- interface static constructor
ms.assetid: 1f031cb2-e94f-43dc-819b-44cf2faaaa49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: e2da339259efd77ea7992e63e6137a15017fdc31
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46402841"
---
# <a name="how-to-define-an-interface-static-constructor-ccli"></a>Практическое руководство. Определение статического конструктора интерфейса (C++/CLI)

Интерфейс может иметь статический конструктор, который может использоваться для инициализации статических элементов данных.  Статический конструктор будет вызываться не более одного раза и будет вызываться до в первый раз доступ к члену статического интерфейс.

## <a name="example"></a>Пример

```
// mcppv2_interface_class2.cpp
// compile with: /clr
using namespace System;

interface struct MyInterface {
   static int i;
   static void Test() {
      Console::WriteLine(i);
   }

   static MyInterface() {
      Console::WriteLine("in MyInterface static constructor");
      i = 99;
   }
};

ref class MyClass : public MyInterface {};

int main() {
   MyInterface::Test();
   MyClass::MyInterface::Test();

   MyInterface ^ mi = gcnew MyClass;
   mi->Test();
}
```

```Output
in MyInterface static constructor
99
99
99
```

## <a name="see-also"></a>См. также

[класс интерфейса](../windows/interface-class-cpp-component-extensions.md)