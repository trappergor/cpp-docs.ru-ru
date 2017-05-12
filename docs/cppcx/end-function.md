---
title: "Функция end | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::end"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Функция end"
ms.assetid: fb837bff-fc76-4bae-9096-facf0e03041c
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Функция end
Возвращает итератор, указывающий на позицию после конечного элемента коллекции, для доступа к которой используется указанный параметр интерфейса.  
  
## Синтаксис  
  
```  
  
template <typename T>  
    ::Platform::Collections::VectorIterator<T>   
    end(  
        IVector<T>^ v       );  
  
template <typename T>  
    ::Platform::Collections::VectorViewIterator<T>   
    end(  
        IVectorView<T>^ v  
       );  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    end(  
        IIterable<T>^ i  
       );  
  
```  
  
#### Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Коллекция объектов Vector\<T\>\> или VectorView\<T\>, доступ к которым осуществляется через интерфейс IVector\<T\> или IVectorView\<T\>.  
  
 `i`  
 Коллекция произвольных объектов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], доступ к которым осуществляется через интерфейс IIterable\<T\>.  
  
## Возвращаемое значение  
 Итератор, который указывает на позицию после конечного элемента коллекции.  
  
## Заметки  
 Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.  
  
 Объект [Platform::Collections::VectorViewIterator](../cppcx/platform-collections-vectorviewiterator-class.md), возвращаемый `end`, является итератором прокси\-сервера, хранящего элементы типа `VectorProxy<T>`. Однако объект прокси\-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## См. также  
 [Пространство имен Windows::Foundation::Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)