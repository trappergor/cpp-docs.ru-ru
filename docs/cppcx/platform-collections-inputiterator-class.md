---
title: "Класс Platform::Collections::InputIterator | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::InputIterator"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс InputIterator"
ms.assetid: ef72eea4-32a9-42b9-8119-ce87dbdcd3be
caps.latest.revision: 4
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 4
---
# Класс Platform::Collections::InputIterator
Предоставляет InputIterator библиотеки стандартных шаблонов для коллекций, наследуемых от интерфейса [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)].  
  
## Синтаксис  
  
```  
template <  
   typename X  
>  
class InputIterator;  
```  
  
#### Параметры  
 `X`  
 Имя типа класса шаблона InputIterator.  
  
## Члены  
  
### Общедоступные определения типов  
  
|Имя|Описание|  
|---------|--------------|  
|`difference_type`|Различие указателя \(ptrdiff\_t\).|  
|`iterator_category`|Категория итератора ввода \(:: std::input\_iterator\_tag\).|  
|`pointer`|Указатель на `const``X`.|  
|`reference`|Ссылка на `const``X`.|  
|`value_type`|Имя типа `X`.|  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор InputIterator::InputIterator](../cppcx/inputiterator-inputiterator-constructor.md)|Инициализирует новый экземпляр класса InputIterator.|  
  
### Открытые операторы  
  
|Имя|Описание|  
|---------|--------------|  
|[InputIterator::operator\!\= \- оператор](../cppcx/inputiterator-operator-inequality-operator.md)|Указывает, отличен ли текущий объект InputIterator от указанного объекта InputIterator.|  
|[Оператор InputIterator::operator\*](../cppcx/inputiterator-operator-decrementoperator.md)|Извлекает ссылку на элемент, указанный текущим итератором InputIterator.|  
|[InputIterator::operator\+\+ \- оператор](../cppcx/inputiterator-operator-increment-operator.md)|Выполняет приращение текущего итератора InputIterator.|  
|[InputIterator::operator\=\= \- оператор](../cppcx/inputiterator-operator-equality-operator.md)|Указывает, равен ли текущий объект InputIterator указанному объекту InputIterator.|  
|[InputIterator::operator\-\> \- оператор](../cppcx/inputiterator-operator-arrow-operator.md)|Извлекает адрес элемента, на который ссылается текущий итератор InputIterator.|  
  
## Иерархия наследования  
 `InputIterator`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)