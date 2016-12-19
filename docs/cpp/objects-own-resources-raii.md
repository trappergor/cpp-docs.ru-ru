---
title: "Собственные ресурсы объекта (RAII) | Microsoft Docs"
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
ms.assetid: f86b484e-5a27-4c3b-a92a-dfaa5dd6d93a
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Собственные ресурсы объекта (RAII)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Убедитесь, что объекты собственные ресурсы.  Этот принцип также называются «получение ресурса инициализация» или «RAII».  
  
## Пример  
 Передайте каждый «новый» объект в качестве аргумента конструктора в другой именованному объекту, которому принадлежит данный \(почти всегда unique\_ptr\).  
  
```cpp  
void f() {  
  unique_ptr<widget> p( new widget(…) );  
  my_class x( new widget() );  
  …  
} // automatic destruction and deallocation for both widget objects  
  // automatic exception safety, as if “finally { p->dispose(); x.w.dispose(); }”  
  
```  
  
 Всегда немедленно передайте новый ресурс в любой другой объект, которому принадлежит данный элемент.  
  
```cpp  
void g() {  
  other_class y( OpenFile() );  
  …  
} // automatic closing and release for file resource  
  // automatic exception safety, as if “finally { y.file.dispose(); }”  
  
```  
  
## См. также  
 [Возвращение к C\+\+](../Topic/Welcome%20Back%20to%20C++%20\(Modern%20C++\).md)   
 [Справочник по языку C\+\+](../cpp/cpp-language-reference.md)   
 [Стандартная библиотека C\+\+](../standard-library/cpp-standard-library-reference.md)