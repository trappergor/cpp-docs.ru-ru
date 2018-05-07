---
title: Закрытые виртуальные функции | Документы Microsoft
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
ms.openlocfilehash: 97b4d7d9f47901fa69aa50bfc6f405355cf378b8
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="private-virtual-functions"></a>Закрытые виртуальные функции
Способ обработки закрытых виртуальных функций в производных классах отличается от управляемых расширений для C++ к Visual C++.  
  
 В управляемых расширениях уровень доступа, виртуальной функции не ограничивает возможности ее переопределения в производном классе. В новом синтаксисе виртуальная функция не может переопределить виртуальную функцию базового класса, нельзя получить доступ. Пример:  
  
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
  
 Нет отсутствует фактическое сопоставление структур в новом синтаксисе такого рода. Один просто приходится выполнять члены базового класса доступны - то есть, отличным от private. Унаследованные методы не нужно иметь тот же уровень доступа. В этом примере наиболее эффективным решением изменение — чтобы сделать элемент MyBaseClass с помощью модификатора `protected`. Таким образом Общие программы доступа к этому методу посредством MyBaseClass с помощью модификатора по-прежнему запрещено.  
  
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
  
 Обратите внимание, что отсутствие явных `virtual` ключевое слово в базовом классе, в новом синтаксисе создает предупреждающее сообщение.  
  
## <a name="see-also"></a>См. также  
 [Объявления членов в пределах класса или интерфейса (C++/CLI)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 