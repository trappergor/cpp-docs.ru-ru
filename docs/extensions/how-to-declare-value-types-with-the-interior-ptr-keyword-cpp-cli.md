---
title: Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- _ptr keyword
- value types, declaring
ms.assetid: 49eea66e-eeba-49bd-95b0-ba297be436e3
ms.openlocfilehash: 46f8c39affe5a3c0ad8648162f0fde5371eb30ca
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195581"
---
# <a name="how-to-declare-value-types-with-the-interior_ptr-keyword-ccli"></a>Практическое руководство. Объявление типов значений с использованием ключевого слова interior_ptr (C++/CLI)

**interior_ptr** можно использовать с типом значения.

> [!IMPORTANT]
> Эта возможность языка поддерживается параметром компилятора `/clr`, а параметром компилятора `/ZW` не поддерживается.

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере C++/CLI показано использование **interior_ptr** с типом значения.

### <a name="code"></a>Код

```cpp
// interior_ptr_value_types.cpp
// compile with: /clr
value struct V {
   V(int i) : data(i){}
   int data;
};

int main() {
   V v(1);
   System::Console::WriteLine(v.data);

   // pointing to a value type
   interior_ptr<V> pv = &v;
   pv->data = 2;

   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);

   // pointing into a value type
   interior_ptr<int> pi = &v.data;
   *pi = 3;
   System::Console::WriteLine(*pi);
   System::Console::WriteLine(v.data);
   System::Console::WriteLine(pv->data);
}
```

```Output
1
2
2
3
3
3
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В типе значения **`this`** указатель принимает значение interior_ptr.

В теле нестатической функции-члена типа значения `V` **`this`** — это выражение типа, `interior_ptr<V>` значение которого является адресом объекта, для которого вызывается функция.

### <a name="code"></a>Код

```cpp
// interior_ptr_value_types_this.cpp
// compile with: /clr /LD
value struct V {
   int data;
   void f() {
      interior_ptr<V> pv1 = this;
      // V* pv2 = this;   error
   }
};
```

## <a name="example"></a>Пример

### <a name="description"></a>Описание

В следующем примере показано использование оператора взятия адреса со статическими членами.

Адрес статического члена типа Visual C++ создает собственный указатель.  Адрес статического члена типа значения является управляемым указателем, так как член типа значения выделяется в куче среды выполнения и может быть перемещен сборщиком мусора.

### <a name="code"></a>Код

```cpp
// interior_ptr_value_static.cpp
// compile with: /clr
using namespace System;
value struct V { int i; };

ref struct G {
   static V v = {22};
   static int i = 23;
   static String^ pS = "hello";
};

int main() {
   interior_ptr<int> p1 = &G::v.i;
   Console::WriteLine(*p1);

   interior_ptr<int> p2 = &G::i;
   Console::WriteLine(*p2);

   interior_ptr<String^> p3 = &G::pS;
   Console::WriteLine(*p3);
}
```

```Output
22
23
hello
```

## <a name="see-also"></a>См. также раздел

[interior_ptr (C++/CLI)](interior-ptr-cpp-cli.md)
