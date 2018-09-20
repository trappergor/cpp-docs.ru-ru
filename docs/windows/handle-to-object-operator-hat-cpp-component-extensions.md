---
title: Оператор дескриптора объекта (^) (расширения компонентов C++) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- ^ handle to object [C++]
ms.assetid: 70c411e6-be57-4468-a944-6ea7be89f392
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: fa72b6ec2983c0d7b9850578e743d03b7e3946e3
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46410862"
---
# <a name="handle-to-object-operator---c-component-extensions"></a>Оператор дескриптора объекта (^) (расширения компонентов C++)

*Декларатор дескриптора* (`^`, произносится «крышка»), изменяет тип [описатель](../cpp/overview-of-declarators.md) означает, что объявленного объекта должны автоматически удаляться при система определяет, что объект является больше не доступен.

## <a name="accessing-the-declared-object"></a>Доступ к объявленному объекту

Переменная, объявленная с декларатором дескриптора, ведет себя как указатель на объект. Но она ссылается на весь объект и не может ссылаться на член объекта, а также не поддерживает арифметические операции над указателями. Оператор косвенного обращения (`*`) используется для обращения к объекту, а оператор доступа к членам класса в виде стрелки (`->`) — для обращения к членам объекта.

## <a name="windows-runtime"></a>Среда выполнения Windows

Компилятор использует COM *подсчет ссылок* механизм для определения, если объект больше не используется и могут быть удалены. Это возможно благодаря тому, что объект, производный от интерфейса среды выполнения Windows, является COM-объектом. Число ссылок увеличивается при создании или копировании объекта и уменьшается, когда объекту задается значение NULL или он выходит за пределы области. Если число ссылок становится равным нулю, объект автоматически и немедленно удаляется.

Преимущество декларатора дескриптора состоит в том, что в модели COM необходимо явно управлять счетчиком ссылок для объекта. Этот процесс является достаточно трудоемким и может повлечь за собой появление ошибок. То есть для увеличения и уменьшения счетчика ссылок необходимо вызывать методы объекта AddRef() и Release(). Однако если объект объявляется с декларатором дескриптора, компилятор Visual C++ создает код, который автоматически настраивает счетчик ссылок.

Сведения о том, как создать экземпляр объекта, см. в разделе [ref новый](../windows/ref-new-gcnew-cpp-component-extensions.md).

## <a name="requirements"></a>Требования

Параметр компилятора: `/ZW`

## <a name="common-language-runtime"></a>Среда CLR

Система использует CLR *сборщик мусора* механизм для определения, если объект больше не используется и могут быть удалены. Среда CLR управляет кучей, в которой выделяется память для объектов, а управляемые ссылки (переменные) в программе указывают на расположение объектов в этой куче. Когда объект больше не используется, занимаемая им в куче память освобождается. Периодически сборщик мусора сжимает кучу, чтобы эффективнее использовать освобожденную память. При сжатии кучи объекты могут быть перемещены, и управляемые ссылки будут ссылаться на недействительные расположения. Но сборщик мусора учитывает все расположения, на которые ссылаются управляемые ссылки, и автоматически обновляет их ,чтобы они ссылались на соответствующие объекты в куче.

Поскольку собственные указатели C++ (`*`) и ссылки (`&`) не являются управляемыми ссылками, сборщик мусора не может автоматически обновлять их адреса. Для решения этой проблемы используйте декларатор дескриптора, чтобы задать переменную, которую сборщик мусора будет учитывать и обновлять автоматически.

В Visual C++ 2002 и Visual C++ 2003 для объявления объекта в управляемой куче использовалась команда `__gc *`.  В новом синтаксисе `^` заменяет `__gc *`.

Дополнительные сведения см. в разделе [как: объявление дескрипторов в собственных типов](../dotnet/how-to-declare-handles-in-native-types.md).

### <a name="examples"></a>Примеры

В этом примере показано, как создавать экземпляр ссылочного типа в управляемой куче.  Также в этом примере показано, как можно инициализировать один дескриптор с другим, чтобы существовало две ссылки на один и тот же объект в управляемой куче со сборкой мусора. Обратите внимание, что при назначении [nullptr](../windows/nullptr-cpp-component-extensions.md) на один дескриптор не помечает объект для сборки мусора.

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

В этом примере показано, что в распространенных случаях C++ с помощью `void*` указатель мыши на любой объект заменяется `Object^`, который может содержать дескриптор на любой ссылочный класс. Также в нем показано, что все типы, такие как массивы и делегаты, можно преобразовывать в дескриптор объекта.

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

В этом примере показано, что собственную ссылку (`&`) не удается привязать к **int** член управляемого типа, как **int** может храниться в куче со сборкой мусора, и не могут отслеживать собственные ссылки Перемещение объектов в управляемой куче. Чтобы исправить эту проблему, используйте локальную переменную или измените `&` на `%`, что сделает эту ссылку отслеживаемой.

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

[Расширения компонентов для платформ среды выполнения](../windows/component-extensions-for-runtime-platforms.md)<br/>
[Оператор отслеживания ссылок](../windows/tracking-reference-operator-cpp-component-extensions.md)