---
title: "Vector::Vector - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::Vector - конструктор"
ms.assetid: 5454433d-e206-45ea-bc8b-bb5a7bf38c17
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::Vector - конструктор
Инициализирует новый экземпляр класса Vector.  
  
## Синтаксис  
  
```  
Vector();  
  
explicit Vector(  
    unsigned int size  
    );  
  
Vector(  
    unsigned int size,  
    T value  
    );  
  
template <typename U> explicit Vector(  
    const ::std::vector<U>& v  
    );  
  
template <typename U> explicit Vector(  
    std::vector<U>&& v  
    );  
  
Vector(  
    const T * ptr,  
    unsigned int size  
    );  
  
template <size_t N> explicit Vector(  
    const T(&arr)[N]  
    );  
  
template <size_t N> explicit Vector(  
    const std::array<T, N>& a  
    );  
  
explicit Vector(  
    const Array<T>^ arr  
    );  
  
template <typename InIt> Vector(  
    InIt first,  
    InIt last  
    );  
  
Vector(  
    std::initializer_list<T> il  
    );  
```  
  
#### Параметры  
 a  
 Массив [std::array](../standard-library/array-class-stl.md), который будет использован для инициализации объекта Vector.  
  
 a  
 Массив [Platform::Array](../cppcx/platform-array-class.md), который будет использован для инициализации объекта Vector.  
  
 `InIt`  
 Тип коллекции объектов, используемой для инициализации текущего объекта Vector.  
  
 il  
 Список [std::initializer\_list](../standard-library/initializer-list-class.md) объектов типа `T`, которые будут использоваться для инициализации объекта Vector.  
  
 `N`  
 Количество элементов в коллекции объектов, используемой для инициализации текущего объекта Vector.  
  
 `size`  
 Количество элементов в объекте Vector.  
  
 `value`  
 Значение, используемое для инициализации каждого элемента в текущем объекте Vector.  
  
 `v`  
 Ссылка [Значения Lvalue и Rvalue](../Topic/Lvalues%20and%20Rvalues%20\(Visual%20C++\).md) на объект [std::vector](../Topic/vector%20Class%201.md), используемый для инициализации текущего объекта Vector.  
  
 `ptr`  
 Указатель на объект `std::vector`, используемый для инициализации текущего объекта Vector.  
  
 `arr`  
 Объект [Platform::Array](../cppcx/platform-array-class.md), используемый для инициализации текущего объекта Vector.  
  
 `a`  
 Объект [std::array](../Topic/vector%20Class%201.md), используемый для инициализации текущего объекта Vector.  
  
 `first`  
 Первый элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип объекта `first` передается с помощью *точной пересылки*. Для получения дополнительной информации см. [Декларатор ссылки Rvalue: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
 `last`  
 Последний элемент в последовательности объектов, используемых для инициализации текущего объекта Vector. Тип объекта `last` передается с помощью *точной пересылки*. Для получения дополнительной информации см. [Декларатор ссылки Rvalue: &&](../Topic/Rvalue%20Reference%20Declarator:%20&&.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)   
 [Коллекции \(C\+\+\/CX\)](../cppcx/collections-c-cx.md)