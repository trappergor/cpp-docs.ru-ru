---
title: "Конструктор UnorderedMap::UnorderedMap | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::UnorderedMap"
ms.assetid: bd62e663-7f3a-43ef-ad6d-8266128c778b
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Конструктор UnorderedMap::UnorderedMap
Инициализирует новый экземпляр класса UnorderedMap.  
  
## Синтаксис  
  
```scr  
UnorderedMap();  
  
  explicit UnorderedMap(  
      size_t n  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  explicit UnorderedMap(  
      const std::unordered_map<K, V, H, P>& m  
      );  
  
  explicit UnorderedMap(  
      std::unordered_map<K, V, H, P>&& m  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h  
      );  
  
  template <typename InIt> UnorderedMap(  
      InIt first,  
      InIt last,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
  
  UnorderedMap(std::initializer_list<  
      std::pair<const K, V>> il  
      );  
  
  UnorderedMap(::std::initializer_list<  
      std::pair<const K, V>> il,  
      size_t n  
      );  
  
  UnorderedMap(  
      ::std::initializer_list< ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h  
      );  
  
  UnorderedMap(::std::initializer_list<  
      ::std::pair<const K, V>> il,  
      size_t n,  
      const H& h,  
      const P& p  
      );  
```  
  
#### Параметры  
 `InIt`  
 Имя типа текущего объекта UnorderedMap.  
  
 `P`  
 Объект функции, который может сравнивать два ключа с целью определения их равенства. Этому параметру по умолчанию присваивается значение [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
 `H`  
 Объект функции, создающий хэш\-значения для ключей. Этому параметру по умолчанию присваивается значение [Класс hash](../Topic/hash%20Class%201.md) для ключевых поддерживаемых этим классом типов.  
  
 `m`  
 Ссылка или [Значения Lvalue и Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) на [std::unordered\_map](../standard-library/unordered-map-class.md), используемый для инициализации текущего объекта UnorderedMap.  
  
 il  
 Список [std::initializer\_list](../standard-library/initializer-list-class.md) объектов [std::pair](../standard-library/pair-structure.md), которые будут использоваться для инициализации сопоставления.  
  
 `first`  
 Итератор ввода первого элемента в диапазоне элементов, используемый для инициализации текущего объекта UnorderedMap.  
  
 `last`  
 Итератор ввода первого элемента после диапазона элементов, используемый для инициализации текущего объекта UnorderedMap.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)   
 [Коллекции](../cppcx/collections-c-cx.md)