---
title: Закрытые виртуальные функции | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-cli
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- virtual functions, private
- derived classes, virtual functions
- access modifiers [C++], for class members
- member access [C++], virtual members
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: 0058d023268fa4d9ca5abe802ff45856e9855dc7
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46418077"
---
# <a name="private-virtual-functions"></a>Закрытые виртуальные функции

Способ обработки закрытые виртуальные функции в производных классах отличается от управляемых расширений для C++ в Visual C++.

В управляемых расширениях уровень доступа виртуальной функции не ограничивает его возможности можно переопределить в производном классе. В новом синтаксисе виртуальная функция не может переопределить виртуальную функцию базового класса, он не может получить доступ к. Пример:

```
__gc class MyBaseClass {
   // inaccessible to a derived class
   virtual void g();
};

__gc class MyDerivedClass : public MyBaseClass {
public:
   // okay in Managed Extensions; g() overrides MyBaseClass::g()
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible
   void g();
};
```

Отсутствует сопоставление реальных подобного рода проектирования в новом синтаксисе. Есть просто сделать члены базового класса доступным — то есть, отличным от private. Унаследованные методы нет необходимости иметь тот же уровень доступа. В этом примере является наименее агрессивные изменения, чтобы сделать элемент MyBaseClass с помощью модификатора `protected`. Таким образом все еще запрещено программы доступа к методу через MyBaseClass с помощью модификатора.

```
ref class MyBaseClass {
protected:
   virtual void g();
};

ref class MyDerivedClass : MyBaseClass {
public:
   virtual void g() override;
};
```

Обратите внимание, что отсутствие явный `virtual` ключевое слово в базовом классе, в новом синтаксисе создает предупреждающее сообщение.

## <a name="see-also"></a>См. также

[Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)
