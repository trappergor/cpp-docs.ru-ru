---
title: Пользовательские операторы (C + +/ CLI) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 7f337051a2a4dab4a323e05d88a530d8f08f0e77
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46438448"
---
# <a name="user-defined-operators-ccli"></a>Пользовательские операторы (C++/CLI)

Определяемые пользователем операторы для управляемых типов разрешены как статические члены и члены экземпляра, или в глобальной области. Тем не менее только статические операторы доступны через метаданные клиенты, написанные на языке, отличном от Visual C++.

В ссылочный тип один из параметров статический определяемый пользователем оператор должен быть один из следующих:

- Дескриптор (`type` ^) к экземпляру данного включающего типа.

- Косвенное обращение типов ссылок (`type`^ & или тип ^ %) на дескриптор экземпляра данного включающего типа.

В тип значения один из параметров статический определяемый пользователем оператор должен быть один из следующих:

- Того же типа в качестве включающего типа значения.

- Косвенное обращение тип указателя (`type`^) для включающего типа.

- Косвенное обращение типов ссылок (`type`% или `type`&) для включающего типа.

- Косвенное обращение типов ссылок (`type`^ % или `type`^ &) для обработки.

Можно определить следующие операторы:

|Оператор|Унарный/бинарный Forms?|
|--------------|--------------------------|
|!|Унарный|
|!=|Binary|
|%|Binary|
|&|Унарный и бинарный|
|&&|Binary|
|*|Унарный и бинарный|
|+|Унарный и бинарный|
|++|Унарный|
|,|Binary|
|-|Унарный и бинарный|
|--|Унарный|
|->|Унарный|
|/|Binary|
|<|Binary|
|<<|Binary|
|\<=|Binary|
|=|Binary|
|==|Binary|
|>|Binary|
|>=|Binary|
|>>|Binary|
|^|Binary|
|False|Унарный|
|true|Унарный|
|&#124;|Binary|
|&#124;&#124;|Binary|
|~|Унарный|

## <a name="example"></a>Пример

```cpp
// mcppv2_user-defined_operators.cpp
// compile with: /clr
using namespace System;
public ref struct X {
   X(int i) : m_i(i) {}
   X() {}

   int m_i;

   // static, binary, user-defined operator
   static X ^ operator + (X^ me, int i) {
      return (gcnew X(me -> m_i + i));
   }

   // instance, binary, user-defined operator
   X^ operator -( int i ) {
      return gcnew X(this->m_i - i);
   }

   // instance, unary, user-defined pre-increment operator
   X^ operator ++() {
      return gcnew X(this->m_i++);
   }

   // instance, unary, user-defined post-increment operator
   X^ operator ++(int i) {
      return gcnew X(this->m_i++);
   }

   // static, unary user-defined pre- and post-increment operator
   static X^ operator-- (X^ me) {
      return (gcnew X(me -> m_i - 1));
   }
};

int main() {
   X ^hX = gcnew X(-5);
   System::Console::WriteLine(hX -> m_i);

   hX = hX + 1;
   System::Console::WriteLine(hX -> m_i);

   hX = hX - (-1);
   System::Console::WriteLine(hX -> m_i);

   ++hX;
   System::Console::WriteLine(hX -> m_i);

   hX++;
   System::Console::WriteLine(hX -> m_i);

   hX--;
   System::Console::WriteLine(hX -> m_i);

   --hX;
   System::Console::WriteLine(hX -> m_i);
}
```

```Output
-5
-4
-3
-2
-1
-2
-3
```

## <a name="example"></a>Пример

В следующем образце показано синтеза оператора, который доступен только при использовании **/CLR** для компиляции. Оператор синтеза создает форму назначения бинарного оператора, если он не определен, где в левой части оператора присваивания имеет тип среды CLR.

```cpp
// mcppv2_user-defined_operators_2.cpp
// compile with: /clr
ref struct A {
   A(int n) : m_n(n) {};
   static A^ operator + (A^ r1, A^ r2) {
      return gcnew A( r1->m_n + r2->m_n);
   };
   int m_n;
};

int main() {
   A^ a1 = gcnew A(10);
   A^ a2 = gcnew A(20);

   a1 += a2;   // a1 = a1 + a2   += not defined in source
   System::Console::WriteLine(a1->m_n);
}
```

```Output
30
```

## <a name="see-also"></a>См. также

[Классы и структуры](../windows/classes-and-structs-cpp-component-extensions.md)