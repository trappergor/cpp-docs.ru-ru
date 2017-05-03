---
title: "Класс Platform::Collections::BackInsertIterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::BackInsertIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс BackInsertIterator"
ms.assetid: aecee1ff-100d-4129-b84b-1966f0923dbf
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::Collections::BackInsertIterator
Представляет итератор, который вставляет, а не перезаписывает элементы в конец упорядоченной коллекции.  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
class BackInsertIterator : public ::std::iterator< ::std::output_iterator_tag, void, void, void, void>;  
```  
  
#### Параметры  
 `T`  
 Тип элемента в текущей коллекции.  
  
## Заметки  
 Класс BackInsertIterator реализует правила, необходимые для [Класс back\_insert\_iterator](../standard-library/back-insert-iterator-class.md).  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор BackInsertIterator::BackInsertIterator](../cppcx/backinsertiterator-backinsertiterator-constructor.md)|Инициализирует новый экземпляр класса BackInsertIterator.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[BackInsertIterator::operator\* \- оператор](../cppcx/backinsertiterator-operator-dereference-operator.md)|Получает ссылку на текущий объект BackInsertIterator.|  
|[BackInsertIterator::operator\+\+ \- оператор](../cppcx/backinsertiterator-operator-increment-operator.md)|Возвращает ссылку на текущий объект BackInsertIterator. Итератор не изменяется.|  
|[BackInsertIterator::operator\= \- оператор](../cppcx/backinsertiterator-operator-assign-operator.md)|Добавляет указанный объект в конец текущей упорядоченной коллекции.|  
  
## Иерархия наследования  
 `BackInsertIterator`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)