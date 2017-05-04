---
title: "Класс Platform::Collections::VectorViewIterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorViewIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс VectorViewIterator"
ms.assetid: be3aa1ae-e6ba-4a06-8d6b-86d8128026f7
caps.latest.revision: 6
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 6
---
# Класс Platform::Collections::VectorViewIterator
Предоставляет итератор библиотеки стандартных шаблонов для объектов, производных от интерфейса [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]`IVectorView`.  
  
 `ViewVectorIterator` — это итератор прокси\-сервера, который хранит элементы типа `VectorProxy<T>`. Однако объект прокси\-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
class VectorViewIterator;  
```  
  
#### Параметры  
 `T`  
 Имя типа класса шаблона VectorViewIterator.  
  
## Члены  
  
### Общедоступные определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|`difference_type`|Различие указателя \(ptrdiff\_t\).|  
|`iterator_category`|Категория итератора произвольного доступа \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Указатель на внутренний тип, необходимый для реализации итератора VectorViewIterator.|  
|`reference`|Ссылка на внутренний тип, необходимый для реализации итератора VectorViewIterator.|  
|`value_type`|Имя типа `T`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorViewIterator::VectorViewIterator \- конструктор](../cppcx/vectorviewiterator-vectorviewiterator-constructor.md)|Инициализирует новый экземпляр класса VectorViewIterator.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorViewIterator::operator\- \- оператор](../cppcx/vectorviewiterator-operator-minus-operator.md)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|  
|[Оператор VectorViewIterator::operator\-\-](../cppcx/vectorviewiterator-operator-decrement-operator.md)|Выполняет уменьшение текущего итератора VectorViewIterator.|  
|[VectorViewIterator::operator\!\= \- оператор](../cppcx/vectorviewiterator-operator-inequality-operator.md)|Указывает, отличен ли текущий объект VectorViewIterator от указанного объекта VectorViewIterator.|  
|[Оператор VectorViewIterator::operator\*](../cppcx/vectorviewiterator-operator-dereference-operator.md)|Извлекает ссылку на элемент, указанный текущим итератором VectorViewIterator.|  
|[VectorViewIterator::operatorOperator](../cppcx/vectorviewiterator-operatoroperator.md)|Извлекает ссылку на элемент, удаленный от текущего итератора VectorViewIterator на указанную величину смещения.|  
|[VectorViewIterator::operator\+ \- оператор](../cppcx/vectorviewiterator-operator-plus-operator.md)|Возвращает объект VectorViewIterator, указывающий на элемент с заданным смещением от указанного объекта VectorViewIterator.|  
|[VectorViewIterator::operator\+\+ \- оператор](../cppcx/vectorviewiterator-operator-increment-operator.md)|Выполняет приращение текущего итератора VectorViewIterator.|  
|[VectorViewIterator::operator\+\= \- оператор](../cppcx/vectorviewiterator-operator-plus-assign-operator.md)|Увеличивает текущий итератор VectorViewIterator на указанную величину смещения.|  
|[VectorViewIterator::operator\< \- оператор](../cppcx/vectorviewiterator-operator-less-than-operator.md)|Указывает, действительно ли текущий объект VectorViewIterator меньше, чем указанный объект VectorViewIterator.|  
|[VectorViewIterator::operator\<\= \- оператор](../cppcx/vectorviewiterator-operator-less-than-or-equals-operator.md)|Указывает, действительно ли текущий объект VectorViewIterator меньше указанного объекта VectorViewIterator или равен ему.|  
|[VectorViewIterator::operator\-\= \- оператор](../cppcx/vectorviewiterator-operator-subtract-assign-operator.md)|Уменьшает текущий итератор VectorViewIterator на указанную величину смещения.|  
|[Оператор VectorViewIterator::operator\=\=](../cppcx/vectorviewiterator-operator-equality-operator.md)|Указывает, равен ли текущий объект VectorViewIterator указанному объекту VectorViewIterator.|  
|[Метод VectorViewIterator::operator\>](../cppcx/vectorviewiterator-operator-greater-than-operator.md)|Указывает, действительно ли текущий объект VectorViewIterator больше, чем указанный объект VectorViewIterator.|  
|[Оператор VectorViewIterator::operator\-\>](../cppcx/vectorviewiterator-operator-arrow-operator.md)|Извлекает адрес элемента, на который ссылается текущий итератор VectorViewIterator.|  
|[VectorViewIterator::operator\>\= \- оператор](../cppcx/vectorviewiterator-operator-greater-than-or-equals-operator.md)|Указывает, действительно ли текущий объект VectorViewIterator больше указанного объекта VectorViewIterator или равен ему.|  
  
## Иерархия наследования  
 `VectorViewIterator`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)