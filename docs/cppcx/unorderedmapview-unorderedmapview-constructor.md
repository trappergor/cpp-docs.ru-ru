---
title: "Конструктор UnorderedMapView::UnorderedMapView | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::UnorderedMapView"
ms.assetid: 408aa6ca-dd8d-4946-a817-42a31d19f429
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор UnorderedMapView::UnorderedMapView
Инициализирует новый экземпляр класса UnorderedMapView.  
  
## Синтаксис  
  
```cpp  
  
UnorderedMapView();  
  
explicit UnorderedMapView(size_t n);  
  
UnorderedMapView(size_t n, const H& h);  
  
UnorderedMapView(size_t n, const H& h, const P& p);  
  
explicit UnorderedMapView(  
    const std::unordered_map<K, V, H, P>& m  
    );  
explicit UnorderedMapView(  
    std::unordered_map<K, V, H, P>&& m  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h  
    );  
  
template <typename InIt> UnorderedMapView(  
    InIt first,  
    InIt last,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
  
UnorderedMapView(  
    std::initializer_list<std::pair<const K, V>> il  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h  
    );  
  
UnorderedMapView(  
    std::initializer_list< std::pair<const K, V>> il,  
    size_t n,  
    const H& h,  
    const P& p  
    );  
```  
  
#### Параметры  
 n  
 Число элементов, для которых необходимо заранее выделить пространство.  
  
 `InIt`  
 Имя типа UnorderedMapView.  
  
 `H`  
 Объект функции, который может создать хэш\-значение для ключа. По умолчанию используется значение [std::hash\<K\>](http://msdn.microsoft.com/ru-ru/54f67435-af9d-4217-a29d-fa4d2491a104) для поддерживаемых `std::hash` типов.  
  
 `P`  
 Тип, предоставляющий объект функции, который может сравнивать два ключа с целью установления их равенства. По умолчанию используется [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
 `m`  
 Ссылка или [Значения Lvalue и Rvalue](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) на [std::unordered\_map](../standard-library/unordered-map-class.md), используемое для инициализации UnorderedMapView.  
  
 `first`  
 Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации UnorderedMapView.  
  
 `last`  
 Итератор ввода первого элемента после диапазона элементов, используемый для инициализации UnorderedMapView.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)