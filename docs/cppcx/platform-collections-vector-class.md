---
title: "Класс Platform::Collections::Vector | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Vector"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс Vector (C++/Cx)"
ms.assetid: aee8c076-9700-47c3-99b6-799fd3edb0ca
caps.latest.revision: 17
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 17
---
# Класс Platform::Collections::Vector
Представляет упорядоченную коллекцию объектов с индивидуальным доступом, осуществляемым при помощи индекса.  
  
## Синтаксис  
  
```  
template <typename T, typename E>  
   ref class Vector sealed;  
```  
  
#### Параметры  
 `T`  
 Тип элементов, содержащихся в объекте Vector.  
  
 `E`  
 Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.  
  
## Заметки  
 Допустимые типы:  
  
1.  целые числа  
  
2.  класс интерфейса ^  
  
3.  открытый ссылочный класс ^  
  
4.  структура значений  
  
5.  открытый класс перечисления  
  
 Класс Vector является конкретной реализацией C\+\+ интерфейса [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410).  
  
 При попытке использовать тип Vector в качестве открытого возвращаемого значения или параметра возникнет ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IVector](http://go.microsoft.com/fwlink/p/?LinkId=262410). Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Vector::Vector \- конструктор](../cppcx/vector-vector-constructor.md)|Инициализирует новый экземпляр класса Vector.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Vector::Append](../cppcx/vector-append-method.md)|Вставляет указанный элемент после последнего элемента текущего объекта Vector.|  
|[Метод Vector::Clear](../cppcx/vector-clear-method.md)|Удаляет все элементы текущего объекта Vector.|  
|[Vector::First \- метод](../cppcx/vector-first-method.md)|Возвращает итератор, указывающий первый элемент объекта Vector.|  
|[Vector::GetAt \- метод](../cppcx/vector-getat-method.md)|Извлекает элемент текущего объекта Vector, указанный заданным индексом.|  
|[Vector::GetMany \- метод](../cppcx/vector-getmany-method.md)|Извлекает последовательность элементов из текущего объекта Vector, начиная с указанного индекса.|  
|[Vector::GetView \- метод](../cppcx/vector-getview-method.md)|Возвращает доступное только для чтения представление объекта Vector, то есть [Platform::Collections::VectorView](../cppcx/platform-collections-vectorview-class.md).|  
|[Vector::IndexOf \- метод](../cppcx/vector-indexof-method.md)|Выполняет поиск указанного элемента в текущем объекте Vector и возвращает его индекс, если он найден.|  
|[Метод Vector::InsertAt](../cppcx/vector-insertat-method.md)|Вставляет указанный элемент в текущий объект Vector после элемента, указанного заданным индексом.|  
|[Метод Vector::ReplaceAll](../cppcx/vector-replaceall-method.md)|Удаляет элементы из текущего объекта Vector, а затем вставляет элементы из указанного массива.|  
|[Метод Vector::RemoveAt](../cppcx/vector-removeat-method.md)|Удаляет элемент, определенный заданным индексом из текущего объекта Vector.|  
|[Метод Vector::RemoveAtEnd](../cppcx/vector-removeatend-method.md)|Удаляет элемент в конце текущего объекта Vector.|  
|[Метод Vector::SetAt](../cppcx/vector-setat-method.md)|Присваивает указанное значение к элементу текущего объекта Vector, определяемому заданным индексом.|  
|[Метод Vector::Size](../cppcx/vector-size-method.md)|Возвращает количество элементов в текущем объекте Vector.|  
  
### События  
  
|||  
|-|-|  
|Имя|Описание|  
|событие [Windows::Foundation::Collection::VectorChangedEventHandler\<T\>^ VectorChanged](http://go.microsoft.com/fwlink/p/?LinkId=262644)|Происходит при изменении объекта Vector.|  
  
## Иерархия наследования  
 `Vector`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)