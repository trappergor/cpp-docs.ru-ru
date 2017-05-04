---
title: "Класс Platform::WeakReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "Platform::WeakReference"
ms.assetid: 8cfe1977-a8c7-4b7b-b539-25c77ed4c5f1
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::WeakReference
Представляет слабую ссылку на экземпляр класса ссылок.  
  
## Синтаксис  
  
```vb  
class WeakReference  
```  
  
#### Параметры  
  
## Члены  
  
### Конструкторы  
  
|Член|Описание|  
|----------|--------------|  
|[Конструктор WeakReference::WeakReference](../cppcx/weakreference-weakreference-constructor-c-cx.md)|Инициализирует новый экземпляр класса WeakReference.|  
  
### Методы  
  
|Член|Описание|  
|----------|--------------|  
|[Метод WeakReference::Resolve](../cppcx/weakreference-resolve-method-platform-namespace.md)|Возвращает дескриптор базовому классу ссылок или значение nullptr, если объект больше не существует.|  
  
### Операторы  
  
|Член|Описание|  
|----------|--------------|  
|[WeakReference::operator\=](../cppcx/weakreference-operator-assign.md)|Присваивает новое значение объекту WeakReference.|  
  
## Заметки  
 Класс WeakReference сам не является классом ссылок и поэтому не наследуется от Platform::Object^ и не может использоваться в сигнатуре открытого метода.  
  
## См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)