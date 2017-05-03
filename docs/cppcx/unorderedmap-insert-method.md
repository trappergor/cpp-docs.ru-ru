---
title: "Метод UnorderedMap::Insert | Microsoft Docs"
ms.custom: ""
ms.date: "12/13/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap::Insert"
ms.assetid: 89d55301-3cad-4877-825b-35096a1dd740
caps.latest.revision: 3
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Метод UnorderedMap::Insert
Добавляет в текущий объект UnorderedMap указанную пару "ключ\-значение".  
  
## Синтаксис  
  
```cpp  
  
virtual bool Insert(  
   K key,   
   V value  
);  
```  
  
#### Параметры  
 `key`  
 Ключ из пары "ключ\-значение". Тип `key` является именем типа *K*  
  
 `value`  
 Значение из пары "ключ\-значение". Тип `value` является именем типа *V*  
  
## Возвращаемое значение  
 Значение `true`, если ключ существующего элемента в текущем объекте Map совпадает с `key` и значение в этом элементе совпадает с `value`. Значение `false`, если в текущем объекте Map нет элемента, соответствующего ключу `key`, и из параметров `key` и `value` создана пара "ключ\-значение" и добавлена в текущий объект UnorderedMap.  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections