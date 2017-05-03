---
title: "Метод UnorderedMapView::HasKey | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView::HasKey"
ms.assetid: 4704da18-8606-4df7-be51-d125b2e4aee0
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMapView::HasKey
Определяет, содержит ли текущий объект UnorderedMap указанный ключ.  
  
## Синтаксис  
  
```cpp  
  
bool HasKey(  
   K key  
);  
```  
  
#### Параметры  
 `key`  
 Ключ, используемый для поиска элемента. Тип `key` является именем типа *K*.  
  
## Возвращаемое значение  
 Значение `true`, если ключ найден; в противном случае — значение `false`.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Класс Platform::Collections::UnorderedMap](../cppcx/platform-collections-unorderedmap-class.md)   
 [Коллекции](../cppcx/collections-c-cx.md)   
 [Windows::Foundation::Collections::IKeyValuePair \< K, V \>](http://msdn.microsoft.com/library/windows/apps/br226031.aspx)