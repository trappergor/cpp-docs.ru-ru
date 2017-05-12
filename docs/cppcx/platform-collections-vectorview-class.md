---
title: "Класс Platform::Collections::VectorView | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::VectorView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "VectorView - класс"
ms.assetid: 05cd461d-dce7-49d3-b0e7-2e5c78ed8192
caps.latest.revision: 8
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 8
---
# Класс Platform::Collections::VectorView
Представляет доступное только для чтения представление упорядоченной коллекции объектов, в которой возможен доступ к каждому отдельному объекту по его индексу. Тип каждого объекта в коллекции задается параметром шаблона.  
  
## Синтаксис  
  
```  
template <typename T, typename E>  
   ref class VectorView sealed;  
```  
  
#### Параметры  
 `T`  
 Тип элементов, содержащихся в объекте `VectorView`.  
  
 `E`  
 Определяет бинарный предикат для проверки равенства со значениями типа `T`. Значение по умолчанию — `std::equal_to<T>`.  
  
## Заметки  
 Класс `VectorView` реализует интерфейс [Windows::Foundation::Collections::IVectorView\<T\>](http://go.microsoft.com/fwlink/p/?LinkId=262411) и поддержку итераторов библиотеки стандартных шаблонов.  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorView::VectorView \- конструктор](../cppcx/vectorview-vectorview-constructor.md)|Инициализирует новый экземпляр класса VectorView.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[VectorView::First \- метод](../cppcx/vectorview-first-method.md)|Возвращает итератор, указывающий первый элемент объекта VectorView.|  
|[VectorView::GetAt \- метод](../cppcx/vectorview-getat-method.md)|Извлекает элемент текущего VectorView, указанный заданным индексом.|  
|[VectorView::GetMany \- метод](../cppcx/vectorview-getmany-method.md)|Извлекает последовательность элементов из текущего объекта VectorView, начиная с указанного индекса.|  
|[VectorView::IndexOf \- метод](../cppcx/vectorview-indexof-method.md)|Выполняет поиск указанного элемента в текущем объекте VectorView и возвращает его индекс, если он найден.|  
|[Метод VectorView::Size](../cppcx/vectorview-size-method.md)|Возвращает количество элементов в текущем объекте VectorView.|  
  
## Иерархия наследования  
 `VectorView`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)