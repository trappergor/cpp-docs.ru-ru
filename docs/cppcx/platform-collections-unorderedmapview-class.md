---
title: "Класс Platform::Collections::UnorderedMapView | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMapView"
ms.assetid: 545a3725-2efd-4cc1-b590-4a7cd2351f61
caps.latest.revision: 5
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 5
---
# Класс Platform::Collections::UnorderedMapView
Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ\-значение".  
  
## Синтаксис  
  
```cpp  
template <  
   typename K,  
   typename V,  
   typename C = ::std::equal_to<K>  
>  
ref class UnorderedMapView sealed;  
```  
  
#### Параметры  
 `K`  
 Тип ключа в паре "ключ\-значение".  
  
 `V`  
 Тип значения в паре "ключ\-значение".  
  
 `C`  
 Тип, предоставляющий объект функции, который может сравнивать два ключевых значения для определения равенства. По умолчанию используется [std::equal\_to\<K\>](../standard-library/equal-to-struct.md)  
  
## Заметки  
 UnorderedMapView — это конкретная реализация интерфейса [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), передаваемая через двоичный интерфейс приложения \(ABI\). Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Конструктор UnorderedMapView::UnorderedMapView](../cppcx/unorderedmapview-unorderedmapview-constructor.md)|Инициализирует новый экземпляр класса UnorderedMapView.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод UnorderedMapView::First](../cppcx/unorderedmapview-first-method.md)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|  
|[Метод UnorderedMapView::HasKey](../cppcx/unorderedmapview-haskey-method.md)|Определяет, содержит ли текущий объект UnorderedMapView указанный ключ.|  
|[Метод UnorderedMapView::Lookup](../cppcx/unorderedmapview-lookup-method.md)|Извлекает элемент по указанному ключу в текущем объекте UnorderedMapView.|  
|[Метод UnorderedMapView::Size](../cppcx/unorderedmapview-size-method.md)|Возвращает количество элементов в текущем объекте UnorderedMapView.|  
|[Метод UnorderedMapView::Split](../cppcx/unorderedmapview-split-method.md)|Разделяет исходный объект UnorderedMapView на два объекта UnorderedMapView.|  
  
## Иерархия наследования  
 `UnorderedMapView`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)   
 [Windows::Foundation::IMapView](http://go.microsoft.com/fwlink/p/?LinkId=262409)