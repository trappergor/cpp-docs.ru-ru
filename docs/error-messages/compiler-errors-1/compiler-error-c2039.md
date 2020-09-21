---
title: Ошибка компилятора C2039
ms.date: 11/04/2016
f1_keywords:
- C2039
helpviewer_keywords:
- C2039
ms.assetid: f9dfd521-9b36-4454-a69c-d63f45b606bb
ms.openlocfilehash: 6dc79db11f08ce00cdb86e930173c052cd5187ed
ms.sourcegitcommit: 72161bcd21d1ad9cc3f12261aa84a5b026884afa
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/17/2020
ms.locfileid: "90742688"
---
# <a name="compiler-error-c2039"></a>Ошибка компилятора C2039

"идентификатор1": не является членом "идентификатор2"

Код неправильно вызывает или ссылается на член структуры, класса или объединения.

## <a name="examples"></a>Примеры

Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039.cpp
struct S {
   int mem0;
} s, *pS = &s;

int main() {
   pS->mem1 = 0;   // C2039 mem1 is not a member
   pS->mem0 = 0;   // OK
}
```

Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039_b.cpp
// compile with: /clr
using namespace System;
int main() {
   Console::WriteLine( "{0}", DateTime::get_Now());   // C2039
   Console::WriteLine( "{0}", DateTime::Now);   // OK
   Console::WriteLine( "{0}", DateTime::Now::get());   // OK
}
```

Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039_c.cpp
// compile with: /clr /c
ref struct S {
   property int Count {
     int get();
     void set(int i){}
   };
};

int S::get_Count() { return 0; }   // C2039
int S::Count::get() { return 0; }   // OK
```

C2039 также может возникать при попытке неправильного доступа к индексатору по умолчанию. В следующем примере определяется компонент, написанный на языке C#.

```
// C2039_d.cs
// compile with: /target:library
// a C# program
[System.Reflection.DefaultMember("Item")]
public class B {
   public int Item {
      get { return 13; }
      set {}
   }
};
```

Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039_e.cpp
// compile with: /clr
using namespace System;
#using "c2039_d.dll"

int main() {
   B ^ b = gcnew B;
   int n = b->default;   // C2039
   // try the following line instead
   // int n = b->Item;
   Console::WriteLine(n);
}
```

C2039 также может возникать при использовании универсальных шаблонов. Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039_f.cpp
// compile with: /clr
interface class I {};

ref struct R : public I {
   virtual void f3() {}
};

generic <typename T>
where T : I
void f(T t) {
   t->f3();   // C2039
   safe_cast<R^>(t)->f3();   // OK
}

int main() {
   f(gcnew R());
}
```

C2039 может возникать при попытке освободить управляемые или неуправляемые ресурсы. Дополнительные сведения см. в разделе [деструкторы и методы завершения](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Destructors_and_finalizers).

Следующий пример приводит к возникновению ошибки C2039.

```cpp
// C2039_g.cpp
// compile with: /clr
using namespace System;
using namespace System::Threading;

void CheckStatus( Object^ stateInfo ) {}

int main() {
   ManualResetEvent^ event = gcnew ManualResetEvent( false );
   TimerCallback^ timerDelegate = gcnew TimerCallback( &CheckStatus );
   Timer^ stateTimer = gcnew Timer( timerDelegate, event, 1000, 250 );

   ((IDisposable ^)stateTimer)->Dispose();   // C2039

   stateTimer->~Timer();   // OK
}
```
