---
title: "Класс Platform::Collections::VectorIterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс VectorIterator"
ms.assetid: d531cb42-27e0-48a6-bf5e-c265891a18ff
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс Platform::Collections::VectorIterator
Предоставляет итератор библиотеки стандартных шаблонов для объектов, наследуемых от интерфейса IVector [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
 VectorIterator — это итератор прокси\-сервера, который хранит элементы типа VectorProxy\<T\>. Однако объект прокси\-сервера практически никогда не отображается в пользовательском коде. Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Синтаксис  
  
```  
template <  
   typename T  
>  
class VectorIterator;  
```  
  
#### Параметры  
 `T`  
 Имя типа класса шаблона VectorIterator.  
  
## Члены  
  
### Общедоступные определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|`difference_type`|Различие указателя \(ptrdiff\_t\).|  
|`iterator_category`|Категория итератора произвольного доступа \(::std::random\_access\_iterator\_tag\).|  
|`pointer`|Указатель на внутренний тип, Platform::Collections::Details::VectorProxy\<T\>, необходимый для реализации итератора VectorIterator.|  
|`reference`|Ссылка на внутренний тип, Platform::Collections::Details::VectorProxy\<T\>, необходимый для реализации итератора VectorIterator.|  
|`value_type`|Имя типа `T`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorIterator::VectorIterator \- конструктор](../cppcx/vectoriterator-vectoriterator-constructor.md)|Инициализирует новый экземпляр класса VectorIterator.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorIterator::operator\- \- оператор](../cppcx/vectoriterator-operator-minus-operator.md)|Вычитает указанное количество элементов из текущего итератора, возвращая новый итератор, или вычитает указанный итератор из текущего итератора, возвращая количество элементов между итераторами.|  
|[VectorIterator::operator\-\- \- оператор](../cppcx/vectoriterator-operator-decrement-operator.md)|Выполняет уменьшение текущего итератора VectorIterator.|  
|[Оператор VectorIterator::operator\!\=](../cppcx/vectoriterator-operator-inequality-operator.md)|Указывает, отличен ли текущий объект VectorIterator от указанного объекта VectorIterator.|  
|[Оператор VectorIterator::operator\*](../cppcx/vectoriterator-operator-dereference-operator.md)|Извлекает ссылку на элемент, указанный текущим итератором VectorIterator.|  
|[VectorIterator::operatorOperator](../cppcx/vectoriterator-operatoroperator.md)|Извлекает ссылку на элемент, отстоящий от текущего итератора VectorIterator на указанную величину смещения.|  
|[\(DELETE\) Оператор VectorIterator::operator\+](http://msdn.microsoft.com/ru-ru/b0b1af2c-e2a8-4876-99dc-7351bfc46ce4)|Возвращает объект VectorIterator, указывающий на элемент с заданным смещением от указанного объекта VectorIterator.|  
|[Оператор VectorIterator::operator\+\+](../cppcx/vectoriterator-operator-increment-operator.md)|Выполняет увеличение текущего итератора VectorIterator.|  
|[VectorIterator::operator\+\= \- оператор](../cppcx/vectoriterator-operator-plus-assign-operator.md)|Увеличивает текущий итератор VectorIterator на указанную величину смещения.|  
|[VectorIterator::operator\< \- оператор](../cppcx/vectoriterator-operator-less-than-operator.md)|Указывает, является ли текущий объект VectorIterator меньшим, чем указанный объект VectorIterator.|  
|[VectorIterator::operator\<\= \- оператор](../cppcx/vectoriterator-operator-less-than-or-equals-operator.md)|Указывает, является ли текущий объект VectorIterator меньшим или равным указанному объекту VectorIterator.|  
|[VectorIterator::operator\-\= \- оператор](../cppcx/vectoriterator-operator-subtract-assign-operator.md)|Уменьшает текущий итератор VectorIterator на указанную величину смещения.|  
|[VectorIterator::operator\=\= \- оператор](../cppcx/vectoriterator-operator-equality-operator.md)|Указывает, равен ли текущий объект VectorIterator указанному объекту VectorIterator.|  
|[Оператор VectorIterator::operator\>](../cppcx/vectoriterator-operator-greater-than-operator.md)|Указывает, действительно ли текущий объект VectorIterator больше, чем указанный объект VectorIterator.|  
|[Оператор VectorIterator::operator\-\>](../cppcx/vectoriterator-operator-arrow-operator.md)|Извлекает адрес элемента, на который ссылается текущий итератор VectorIterator.|  
|[VectorIterator::operator\>\= \- оператор](../cppcx/vectoriterator-operator-greater-than-or-equal-operator.md)|Указывает, действительно ли текущий объект VectorIterator больше указанного объекта VectorIterator или равен ему.|  
  
## Иерархия наследования  
 `VectorIterator`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)