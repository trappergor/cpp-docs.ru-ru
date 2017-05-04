---
title: "VectorView::VectorView - конструктор | Microsoft Docs"
ms.custom: ""
ms.date: "01/24/2017"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView::VectorView - конструктор"
ms.assetid: 5ec14dbc-5f6f-44b6-8fc4-f5a31053eb5f
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# VectorView::VectorView - конструктор
Инициализирует новый экземпляр класса VectorView.  
  
## Синтаксис  
  
```  
VectorView();  
explicit VectorView(  
   UInt32 size  
);  
VectorView(  
   UInt32 size,  
   T value  
);  
explicit VectorView(  
   const ::std::vector<T>& v  
);  
explicit VectorView(  
   ::std::vector<T>&& v  
);  
VectorView(  
   const T * ptr,  
   UInt32 size  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const T (&arr)[N]  
);  
  
template <  
   size_t N  
>  
explicit VectorView(  
   const ::std::array<T,  
   N>& a  
);  
  
explicit VectorView(  
   const ::Platform::Array<T>^ arr  
);  
  
template <  
   typename InIt  
>  
VectorView(  
   InItfirst,  
   InItlast  
);  
  
VectorView(  
   std::initializer_list<T> il  
);  
```  
  
#### Параметры  
 `InIt`  
 Тип коллекции объектов, используемой для инициализации текущего объекта VectorView.  
  
 il  
 Список [std::initializer\_list](../standard-library/initializer-list-class.md), элементы которого будут использоваться для инициализации объекта VectorView.  
  
 `N`  
 Количество элементов в коллекции объектов, используемой для инициализации текущего объекта VectorView.  
  
 `size`  
 Количество элементов в объекте VectorView.  
  
 `value`  
 Значение, используемое для инициализации каждого элемента в текущем объекте VectorView.  
  
 `v`  
 Ссылка [Значения Lvalue и Rvalue](http://msdn.microsoft.com/library/a8843344-cccc-40be-b701-b71f7b5cdcaf) на объект [::std::vector](../Topic/vector%20Class%201.md), используемый для инициализации текущего объекта VectorView.  
  
 `ptr`  
 Указатель на объект `std::vector`, используемый для инициализации текущего объекта VectorView.  
  
 `arr`  
 Объект [Platform::Array](../cppcx/platform-array-class.md), используемый для инициализации текущего объекта VectorView.  
  
 `a`  
 Объект [std::array](../Topic/vector%20Class%201.md), используемый для инициализации текущего объекта VectorView.  
  
 `first`  
 Первый элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип объекта `first` передается с помощью *точной пересылки*. Дополнительные сведения см. в разделе [Декларатор ссылки Rvalue: &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
 `last`  
 Последний элемент в последовательности объектов, используемых для инициализации текущего объекта VectorView. Тип объекта `last` передается с помощью *точной пересылки*. Для получения дополнительной информации см. [Декларатор ссылки Rvalue: &&](~/cpp/rvalue-reference-declarator-amp-amp.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)