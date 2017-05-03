---
title: "WeakReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::operator="
ms.assetid: 20b034d1-8f4f-46ae-81f0-73b76599f86b
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::operator=
Присваивает значение WeakReference.  
  
## Синтаксис  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
## Заметки  
 Последняя перегрузка в списке выше позволяет назначить класс ссылок переменной WeakReference. В этом случае выполняется нисходящее приведения класса ссылок к [Platform::Object](../cppcx/platform-object-class.md)^. Позже исходный тип восстанавливается путем задания его в качестве аргумента для параметра типа в функции\-члене [WeakReference::Resolve\<T\>](../cppcx/weakreference-resolve-method-platform-namespace.md).  
  
## Требования  
 Windows 8.0 или более поздняя версия  
  
## См. также  
 [Класс Platform::WeakReference](../cppcx/platform-weakreference-class.md)