---
title: Оператор дескриптора объекта (^) (C++/CLI и C++/CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
ms.openlocfilehash: bdf19b6b472cd4d224d749f59c75ca77d11c34f8
ms.sourcegitcommit: c6f8e6c2daec40ff4effd8ca99a7014a3b41ef33
ms.translationtype: HT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/24/2019
ms.locfileid: "65516699"
---
# <a name="handle-to-object-operator---ccli-and-ccx"></a>Оператор дескриптора объекта (^) (C++/CLI и C++/CX)

*Декларатор дескриптора* (`^` — "шляпка") изменяет [описатель](../cpp/overview-of-declarators.md) типа и указывает, что объявленный объект будет автоматически удален, когда система определит, что он более недоступен.

## <a name="accessing-the-declared-object"></a>Доступ к объявленному объекту

Переменная, объявленная с декларатором дескриптора, ведет себя как указатель на объект. Но она ссылается на весь объект и не может ссылаться на член объекта, а также не поддерживает арифметические операции над указателями. Оператор косвенного обращения (`*`) используется для обращения к объекту, а оператор доступа к членам класса в виде стрелки (`->`) — для обращения к членам объекта.

## <a name="windows-runtime"></a>Среда выполнения Windows

Компилятор использует механизм *подсчета ссылок* модели COM, чтобы определить, используется ли объект или его можно удалить. Это возможно благодаря тому, что объект, производный от интерфейса среды выполнения Windows, является COM-объектом. Число ссылок увеличивается при создании или копировании объекта и уменьшается, когда объекту задается значение NULL или он выходит за пределы области. Если число ссылок становится равным нулю, объект автоматически и немедленно удаляется.

Преимущество декларатора дескриптора состоит в том, что в модели COM необходимо явно управлять счетчиком ссылок для объекта. Этот процесс является достаточно трудоемким и может повлечь за собой появление ошибок. То есть для увеличения и уменьшения счетчика ссылок необходимо вызывать методы объекта AddRef() и Release(). Однако если объект объявляется с декларатором дескриптора, компилятор создает код, который автоматически настраивает счетчик ссылок.

Подробные сведения о способах создания объекта см. в статье [ref new](ref-new-gcnew-cpp-component-extensions.md).

## <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Система применяет *сборщик мусора* CLR, чтобы определить, используется ли объект или его можно удалить. Среда CLR управляет кучей, в которой выделяется память для объектов, а управляемые ссылки (переменные) в программе указывают на расположение объектов в этой куче. Когда объект больше не используется, занимаемая им в куче память освобождается. Периодически сборщик мусора сжимает кучу, чтобы эффективнее использовать освобожденную память. При сжатии кучи объекты могут быть перемещены, и управляемые ссылки будут ссылаться на недействительные расположения. Но сборщик мусора учитывает все расположения, на которые ссылаются управляемые ссылки, и автоматически обновляет их ,чтобы они ссылались на соответствующие объекты в куче.

Поскольку собственные указатели C++ (`*`) и ссылки (`&`) не являются управляемыми ссылками, сборщик мусора не может автоматически обновлять их адреса. Для решения этой проблемы используйте декларатор дескриптора, чтобы задать переменную, которую сборщик мусора будет учитывать и обновлять автоматически.

Дополнительные сведения см. в разделе [Практическое руководство. Объявление дескрипторов в собственных типах](../dotnet/how-to-declare-handles-in-native-types.md).

### <a name="examples"></a>Примеры

В этом примере показано, как создавать экземпляр ссылочного типа в управляемой куче.  Также в этом примере показано, как можно инициализировать один дескриптор с другим, чтобы существовало две ссылки на один и тот же объект в управляемой куче со сборкой мусора. Обратите внимание, если одному дескриптору присвоить значение [nullptr](nullptr-cpp-component-extensions.md), то объект не будет помечен для обработки сборщиком мусора.

```cpp
// mcppv2_handle.cpp
// compile with: /clr
ref class MyClass {
public:
   MyClass() : i(){}
   int i;
   void Test() {
      i++;
      System::Console::WriteLine(i);
   }
};

int main() {
   MyClass ^ p_MyClass = gcnew MyClass;
   p_MyClass->Test();

   MyClass ^ p_MyClass2;
   p_MyClass2 = p_MyClass;

   p_MyClass = nullptr;
   p_MyClass2->Test();
}
```

```Output
1
2
```

В следующем примере показано, как объявить дескриптор объекта в управляемой куче, если тип объекта является упакованным значением. Также в примере показано, как получить тип значения из упакованного объекта.

```cpp
// mcppv2_handle_2.cpp
// compile with: /clr
using namespace System;

void Test(Object^ o) {
   Int32^ i = dynamic_cast<Int32^>(o);

   if(i)
      Console::WriteLine(i);
   else
      Console::WriteLine("Not a boxed int");
}

int main() {
   String^ str = "test";
   Test(str);

   int n = 100;
   Test(n);
}
```

```Output
Not a boxed int
100
```

В этом примере показано, что обычная практика использования указателя `void*` для ссылки на любой объект в C++ заменена на `Object^`, который может содержать дескриптор на любой ссылочный класс. Также в нем показано, что все типы, такие как массивы и делегаты, можно преобразовывать в дескриптор объекта.

```cpp
// mcppv2_handle_3.cpp
// compile with: /clr
using namespace System;
using namespace System::Collections;
public delegate void MyDel();
ref class MyClass {
public:
   void Test() {}
};

void Test(Object ^ x) {
   Console::WriteLine("Type is {0}", x->GetType());
}

int main() {
   // handle to Object can hold any ref type
   Object ^ h_MyClass = gcnew MyClass;

   ArrayList ^ arr = gcnew ArrayList();
   arr->Add(gcnew MyClass);

   h_MyClass = dynamic_cast<MyClass ^>(arr[0]);
   Test(arr);

   Int32 ^ bi = 1;
   Test(bi);

   MyClass ^ h_MyClass2 = gcnew MyClass;

   MyDel^ DelInst = gcnew MyDel(h_MyClass2, &MyClass::Test);
   Test(DelInst);
}
```

```Output
Type is System.Collections.ArrayList

Type is System.Int32

Type is MyDel
```

В этом примере показано, что дескриптор может быть разыменован и через него можно обратиться к члену.

```cpp
// mcppv2_handle_4.cpp
// compile with: /clr
using namespace System;
value struct DataCollection {
private:
   int Size;
   array<String^>^ x;

public:
   DataCollection(int i) : Size(i) {
      x = gcnew array<String^>(Size);
      for (int i = 0 ; i < Size ; i++)
         x[i] = i.ToString();
   }

   void f(int Item) {
      if (Item >= Size)
      {
         System::Console::WriteLine("Cannot access array element {0}, size is {1}", Item, Size);
         return;
      }
      else
         System::Console::WriteLine("Array value: {0}", x[Item]);
   }
};

void f(DataCollection y, int Item) {
   y.f(Item);
}

int main() {
   DataCollection ^ a = gcnew DataCollection(10);
   f(*a, 7);   // dereference a handle, return handle's object
   (*a).f(11);   // access member via dereferenced handle
}
```

```Output
Array value: 7

Cannot access array element 11, size is 10
```

В этом примере показано, что собственную ссылку (`&`) невозможно привязать к члену управляемого типа **int**, поскольку **int** может располагаться в куче со сборкой мусора, а собственные ссылки не могут отслеживать перемещение объектов в управляемой куче. Чтобы исправить эту проблему, используйте локальную переменную или измените `&` на `%`, что сделает эту ссылку отслеживаемой.

```cpp
// mcppv2_handle_5.cpp
// compile with: /clr
ref struct A {
   void Test(unsigned int &){}
   void Test2(unsigned int %){}
   unsigned int i;
};

int main() {
   A a;
   a.i = 9;
   a.Test(a.i);   // C2664
   a.Test2(a.i);   // OK

   unsigned int j = 0;
   a.Test(j);   // OK
}
```

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](component-extensions-for-runtime-platforms.md)<br/>
[Оператор отслеживания ссылок](tracking-reference-operator-cpp-component-extensions.md)
