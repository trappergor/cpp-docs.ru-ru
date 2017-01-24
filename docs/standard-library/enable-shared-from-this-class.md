---
title: "Класс enable_shared_from_this | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "tr1.enable_shared_from_this"
  - "enable_shared_from_this"
  - "std.tr1.enable_shared_from_this"
  - "memory/std::tr1::enable_shared_from_this"
  - "std::tr1::enable_shared_from_this"
  - "tr1::enable_shared_from_this"
  - "std.enable_shared_from_this"
  - "memory/std::enable_shared_from_this"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "enable_shared_from_this - класс"
  - "enable_shared_from_this - класс [TR1]"
ms.assetid: 9237603d-22e2-421f-b070-838ac006baf5
caps.latest.revision: 22
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Класс enable_shared_from_this
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Помогает сформировать `shared_ptr`.  
  
## Синтаксис  
  
```  
template<class Ty>  
    class enable_shared_from_this {  
public:  
    shared_ptr<Ty> shared_from_this();  
    shared_ptr<const Ty> shared_from_this() const;  
  
protected:  
    enable_shared_from_this();  
    enable_shared_from_this(const enable_shared_from_this&);  
    enable_shared_from_this& operator=(const enable_shared_from_this&);  
    ~enable_shared_from_this();  
    };  
```  
  
#### Параметры  
 `Ty`  
 Тип, управляемый общим указателем.  
  
## Заметки  
 Объекты, производные от `enable_shared_from_this` можно использовать `shared_from_this` методы в функции\-члены для создания [shared\_ptr](../standard-library/shared-ptr-class.md) владельцами экземпляра, владеть с существующими `shared_ptr` владельцев. В противном случае, если создается новый `shared_ptr` с помощью `this`, отличается от существующих `shared_ptr` владельцев, что может привести к недопустимые ссылки или вызвать объект для удаления более одного раза.  
  
 Во избежание случайного нарушения защищены конструктора, деструктора и оператор присваивания. Тип аргумента шаблона `Ty` должен быть типа производного класса.  
  
 Пример использования см. в разделе [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md).  
  
## Требования  
 **Заголовок:** \<память\>  
  
 **Пространство имен:** std  
  
## См. также  
 [enable\_shared\_from\_this::shared\_from\_this](../Topic/enable_shared_from_this::shared_from_this.md)   
 [Класс shared\_ptr](../standard-library/shared-ptr-class.md)