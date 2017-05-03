---
title: "begin - функция | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Windows::Foundation::Collections::begin"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "begin - функция"
ms.assetid: 5a44fb33-e247-49fd-b7a1-4a5b42e9e1e4
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# begin - функция
Возвращает итератор, указывающий на начало коллекции, для доступа к которой используется указанный параметр интерфейса.  
  
## Синтаксис  
  
```  
  
template <typename T>   
    ::Platform::Collections::VectorIterator<T>   
    begin(  
          IVector<T>^ v         );  
  
template <typename T>   
    ::Platform::Collections::VectorViewIterator<T>   
    begin(  
          IVectorView<T>^ v  
         );   
  
template <typename T>   
    ::Platform::Collections::InputIterator<T>   
    begin(  
          IIterable<T>^ i         );  
  
```  
  
#### Параметры  
 `T`  
 Параметр типа шаблона.  
  
 `v`  
 Коллекция объектов Vector\<T\>\> или VectorView\<T\>, доступ к которым осуществляется через интерфейс IVector\<T\> или IVectorView\<T\>.  
  
 `i`  
 Коллекция произвольных объектов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], доступ к которым осуществляется через интерфейс IIterable\<T\>.  
  
## Возвращаемое значение  
 Итератор, который указывает на начало коллекции.  
  
## Заметки  
 Первые две функции шаблона возвращают итераторы, а третья возвращает итератор ввода.  
  
 Объект VectorIterator, который возвращается методом begin, является итератором прокси\-сервера, хранящего элементы типа VectorProxy\<T\>. Однако объект прокси\-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Windows::Foundation::Collections  
  
## См. также  
 [Пространство имен Windows::Foundation::Collections](../cppcx/windows-foundation-collections-namespace-c-cx.md)