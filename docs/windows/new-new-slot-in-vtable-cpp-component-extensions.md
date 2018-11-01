---
title: New (новый слот в vtable) (C + +/ CLI и C + +/ CX)
ms.date: 10/12/2018
ms.topic: reference
helpviewer_keywords:
- new keyword [C++]
ms.assetid: 1a9a5704-f02f-46ae-ad65-f0f2b6dbabc3
ms.openlocfilehash: b143b2ead1165382d0959f4e4c90f1d2e7ea936a
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50487169"
---
# <a name="new-new-slot-in-vtable--ccli-and-ccx"></a>New (новый слот в vtable) (C + +/ CLI и C + +/ CX)

**Новый** слово указывает, что виртуальный член получает новую ячейку в таблице vtable.

## <a name="all-runtimes"></a>Все среды выполнения

(Отсутствуют комментарии для этой возможности языка, которая применяется во всех средах выполнения.)

## <a name="windows-runtime"></a>Среда выполнения Windows

Не поддерживается в среде выполнения Windows.

## <a name="common-language-runtime"></a>Среда CLR

### <a name="remarks"></a>Примечания

В `/clr` компиляции **новый** указывает, что виртуальный член получает новую ячейку в таблице vtable, что функция не переопределяет метод базового класса.

**новый** вызывает модификатор newslot добавляемый IL-код для функции.  Дополнительные сведения о newslot см. в разделе:

- [Метод MethodInfo.GetBaseDefinition](https://msdn.microsoft.com/library/system.reflection.methodinfo.getbasedefinition.aspx)

- [Перечисление пространство](https://msdn.microsoft.com/library/system.reflection.methodattributes.aspx)

### <a name="requirements"></a>Требования

Параметр компилятора: `/clr`

### <a name="examples"></a>Примеры

В следующем примере показано влияние **новый**.

```cpp
// newslot.cpp
// compile with: /clr
ref class C {
public:
   virtual void f() {
      System::Console::WriteLine("C::f() called");
   }

   virtual void g() {
      System::Console::WriteLine("C::g() called");
   }
};

ref class D : public C {
public:
   virtual void f() new {
      System::Console::WriteLine("D::f() called");
   }

   virtual void g() override {
      System::Console::WriteLine("D::g() called");
   }
};

ref class E : public D {
public:
   virtual void f() override {
      System::Console::WriteLine("E::f() called");
   }
};

int main() {
   D^ d = gcnew D;
   C^ c = gcnew D;

   c->f();   // calls C::f
   d->f();   // calls D::f

   c->g();   // calls D::g
   d->g();   // calls D::g

   D ^ e = gcnew E;
   e->f();   // calls E::f
}
```

```Output
C::f() called

D::f() called

D::g() called

D::g() called

E::f() called
```

## <a name="see-also"></a>См. также

[Расширения компонентов для .NET и UWP](../windows/component-extensions-for-runtime-platforms.md)<br/>

[Спецификаторы переопределения](../windows/override-specifiers-cpp-component-extensions.md)