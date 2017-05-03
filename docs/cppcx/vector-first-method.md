---
title: "Vector::First - метод | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector::First"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Vector::First - метод"
ms.assetid: ca6b7b55-dd49-4346-bfa4-d8010b228d44
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Vector::First - метод
Возвращает итератор, указывающий первый элемент объекта Vector.  
  
## Синтаксис  
  
```  
  
virtual Windows::Foundation::Collections::IIterator <T>^   
   First();  
```  
  
## Возвращаемое значение  
 Итератор, указывающий первый элемент объекта Vector.  
  
## Заметки  
 Удобный способ сохранения итератора, возвращаемого методом First\(\), — присвоить возвращаемое значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](~/cpp/auto-cpp.md). Например, `auto x = myVector->First();`. Этому итератору известна длина коллекции.  
  
 При необходимости передать пару итераторов функции STL используйте свободные функции [Windows::Foundation::Collections::begin](../cppcx/begin-function.md) и [Windows::Foundation::Collections::end](../cppcx/end-function.md)  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::Vector](../cppcx/platform-collections-vector-class.md)   
 [Коллекции](../cppcx/collections-c-cx.md)