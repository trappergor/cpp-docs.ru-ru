---
title: Пользовательские операторы (C++/CLI)
ms.date: 11/04/2016
helpviewer_keywords:
- user-defined operators under /clr
ms.assetid: 42f93b4a-6de4-4e34-b07b-5a62ac014f2c
ms.openlocfilehash: ee5aa122983a315e55884c643a9b7894f075e260
ms.sourcegitcommit: 43cee7a0d41a062661229043c2f7cbc6ace17fa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/13/2020
ms.locfileid: "92008950"
---
# <a name="user-defined-operators-ccli"></a>Пользовательские операторы (C++/CLI)

Определяемые пользователем операторы для управляемых типов разрешены как статические члены или члены экземпляра или в глобальной области видимости. Однако только статические операторы доступны через метаданные для клиентов, написанных на языке, отличном от Visual C++.

В ссылочном типе один из параметров статического определяемого пользователем оператора должен быть одним из следующих:

- Маркер ( `type` ^) для экземпляра включающего типа.

- Косвенное обращение ссылочного типа ( `type` ^& или тип ^%) на обработку экземпляра включающего типа.

В типе значения один из параметров статического определяемого пользователем оператора должен быть одним из следующих:

- Того же типа, что и включающий тип значения.

- Косвенное обращение типа указателя ( `type` ^) к включающему типу.

- Косвенное обращение типа ссылки ( `type` % или `type`&) к включающему типу.

- Косвенное обращение ссылочного типа ( `type` ^% или `type` ^&) к этому обработчику.

Можно определить следующие операторы:

|Оператор|Унарные и двоичные формы?|
|--------------|--------------------------|
|!|Унарный|
|!=|Двоичные данные|
|%|Двоичные данные|
|&|Унарный и бинарный|
|&&|Двоичные данные|
|*|Унарный и бинарный|
|+|Унарный и бинарный|
|++|Унарный|
|,|Двоичные данные|
|-|Унарный и бинарный|
|--|Унарный|
|->|Унарный|
|/|Двоичные данные|
|<|Двоичные данные|
|<<|Двоичные данные|
|\<=|Двоичные данные|
|=|Двоичные данные|
|==|Двоичные данные|
|>|Двоичные данные|
|>=|Двоичные данные|
|>>|Двоичные данные|
|^|Двоичные данные|
|false|Унарный|
|Да|Унарный|
|&#124;|Двоичные данные|
|&#124;&#124;|Двоичные данные|
|~|Унарный|

## <a name="example-user-defined-operators"></a>Пример. определяемые пользователем операторы

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

## <a name="example-operator-synthesis"></a>Пример: оператор синтеза операторов

В следующем примере демонстрируется синтез операторов, который доступен только при использовании **/CLR** для компиляции. Синтез оператора создает форму назначения бинарного оператора, если он не определен, где левая часть оператора присваивания имеет тип CLR.

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

[Классы и структуры](../extensions/classes-and-structs-cpp-component-extensions.md)
