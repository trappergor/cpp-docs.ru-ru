---
title: "Метод UnorderedMap::First | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::First"
ms.assetid: 915e771a-cec1-4905-8ecb-76501f63c143
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMap::First
Возвращает итератор, задающий первый элемент [Windows::Foundation::Collections::IKeyValuePair\<K,V\>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx) в неупорядоченном сопоставлении.  
  
## Синтаксис  
  
```cpp  
  
virtual Windows::Foundation::Collections::IIterator<  
Windows::Foundation::Collections::IKeyValuePair<K, V>^>^ First();  
```  
  
## Возвращаемое значение  
 Итератор, указывающий первый элемент в сопоставлении.  
  
## Заметки  
 Удобный способ сохранения итератора, возвращаемого методом First\(\), — присвоить возвращаемое значение переменной, объявленной с помощью ключевого слова вычитания типа [auto](../Topic/auto%20\(C++\).md). Например, `auto x = myUnorderedMap->First();`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::UnorderedMap](../cppcx/platform-collections-unorderedmap-class.md)   
 [Коллекции](../cppcx/collections-c-cx.md)