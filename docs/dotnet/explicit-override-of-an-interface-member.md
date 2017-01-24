---
title: "Явное переопределение элемента интерфейса | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "явное переопределение виртуальных функций"
  - "функции [C++], переопределение"
  - "члены интерфейса, явные переопределения"
  - "переопределение функций"
  - "виртуальные функции, явные переопределения"
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Явное переопределение элемента интерфейса
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)] синтаксис для объявления переопределения элемента интерфейса в классе изменился по сравнению с управляемыми расширениями для C\+\+.  
  
 Часто требуется предоставить два экземпляра элемента интерфейса в классе, который реализует этот интерфейс. Первый используется при управлении объектами классов с помощью дескриптора интерфейса, а второй — при использовании объектов класса через интерфейс классов.  Примеры.  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 В управляемых расширениях это можно выполнить, предоставив явное объявление метода интерфейса и включив в имя метода имя интерфейса.  Имя экземпляра конкретного класса не указывается.  Это снижает необходимость образовывать производный тип для возвращаемого значения `Clone` \(в данном примере\) в случае явного вызова с помощью экземпляра `R`.  
  
 В новом синтаксисе используется новый механизм переопределения, заменивший синтаксис, который использовался в управляемых расширениях.  Этот пример может быть переписан следующим образом:  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Для подобного исправления необходимо, чтобы элемент интерфейса был явно переопределен и чтобы ему было присвоено уникальное имя в классе.  Здесь использовалось странное имя `InterfaceClone`.  Однако поведение остается прежним — с помощью интерфейса `ICloneable` вызывается переименованный элемент `InterfaceClone,`, в то время как с помощью объекта типа `R` вызывается второй экземпляр `Clone`.  
  
## См. также  
 [Объявления членов в пределах класса или интерфейса \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Явные переопределения](../windows/explicit-overrides-cpp-component-extensions.md)