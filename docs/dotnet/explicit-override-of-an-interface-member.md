---
title: Явное переопределение элемента интерфейса | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, explicit overrides
- overriding functions
- interface members, explicit overrides
- functions [C++], overriding
- explicit override of virtual function
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 57c26c1185eff0e88e18ef23cb8506fb1fed407a
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46409029"
---
# <a name="explicit-override-of-an-interface-member"></a>Явное переопределение элемента интерфейса

Синтаксис объявления явное переопределение элемента интерфейса внутри класса отличается от управляемых расширений для C++ в Visual C++.

Часто требуется предоставить два экземпляра члена интерфейса в класс, реализующий интерфейс — один используется, когда объекты класса осуществляется через дескриптор интерфейс, а тот, который используется при использовании объектов класса через интерфейс класса. Пример:

```
public __gc class R : public ICloneable {
   // to be used through ICloneable
   Object* ICloneable::Clone();

   // to be used through an R
   R* Clone();
};
```

В управляемых расширениях это делается путем предоставления явного объявления метода интерфейса с именем метода, с именем интерфейса. Экземпляр данного класса, является неполным. Это избавляет от необходимости нисходящее приведение типа возвращаемого значения `Clone`, в этом примере, в случае явного вызова с помощью экземпляра `R`.

В новом синтаксисе механизм переопределения было введено, заменяет синтаксис управляемых расширений. Наш пример можно переписать следующим образом:

```
public ref class R : public ICloneable {
public:
   // to be used through ICloneable
   virtual Object^ InterfaceClone() = ICloneable::Clone;

   // to be used through an R
   virtual R^ Clone();
};
```

Эта версия требует явного переопределения члена интерфейса присвоено уникальное имя внутри класса. Здесь я предоставил неуклюжим имя `InterfaceClone`. Поведение остается неизменным - вызов через `ICloneable` интерфейс вызывает переименованной `InterfaceClone`, тогда как вызов через объект типа `R` вызывает второй `Clone` экземпляра.

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)<br/>
[Явные переопределения](../windows/explicit-overrides-cpp-component-extensions.md)