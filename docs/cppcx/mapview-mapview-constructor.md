---
title: "MapView::MapView - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "01/25/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MapView::MapView - конструктор"
ms.assetid: 67a3250c-b527-47ac-a103-0fd186046d71
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# MapView::MapView - конструктор
Инициализирует новый экземпляр класса MapView.  
  
## Синтаксис  
  
```  
explicit MapView(  
    const C& comp = C()  
    );  
  
explicit MapView(  
    const ::std::map<K, V, C>& m  
    );  
  
explicit MapView(  
    std::map<K, V, C>&& m  
    );  
  
template <typename InIt> MapView(  
    InIt first,  
    InIt last,  
    const C& comp = C()  
    );  
  
MapView(::std::initializer_list<  
    std::pair<const K, V>> il,  
    const C& comp = C()  
    );  
```  
  
#### Параметры  
 `InIt`  
 Имя типа текущего объекта MapView.  
  
 `comp`  
 Тип, предоставляющий объект функции, который может сравнить два значения элементов в качестве ключей сортировки для определения их относительного порядка в объекте MapView.  
  
 `m`  
 Ссылка или [Значения Lvalue и Rvalue](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) на объект [Класс map](../standard-library/map-class.md), используемый для инициализации текущего объекта MapView.  
  
 `first`  
 Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта MapView.  
  
 `last`  
 Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта MapView.  
  
 il  
 Список [std::initializer\_list\<std::pair\<K,V\>\>](../standard-library/initializer-list-class.md), элементы которого будут вставлены в MapView.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)