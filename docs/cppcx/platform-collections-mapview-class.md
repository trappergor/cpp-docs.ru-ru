---
title: "Класс Platform::Collections::MapView | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::MapView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс MapView"
ms.assetid: 9577dde7-f599-43c6-b1e4-7d653706fd62
caps.latest.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 9
---
# Класс Platform::Collections::MapView
Представляет доступное только для чтения представление на *карте*, которое является коллекцией пар "ключ\-значение".  
  
## Синтаксис  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = ::std::less<K>  
>  
ref class MapView sealed;  
```  
  
#### Параметры  
 `K`  
 Тип ключа в паре "ключ\-значение".  
  
 `V`  
 Тип значения в паре "ключ\-значение".  
  
 `C`  
 Тип, предоставляющий объект функции, который может сравнить значения двух элементов как ключи сортировки, чтобы определить их относительный порядок в объекте MapView. По умолчанию используется значение [::std::less\<K\>](../standard-library/less-struct.md).  
  
## Заметки  
 MapView — это конкретная реализация интерфейса [Windows::Foundation::Collections::IMapView\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262409), передаваемая через двоичный интерфейс приложения \(ABI\). Дополнительные сведения см. в разделе [Collections \(C\+\+\/CX\)](../cppcx/collections-c-cx.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[MapView::MapView \- конструктор](../cppcx/mapview-mapview-constructor.md)|Инициализирует новый экземпляр класса MapView.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод MapView::First](../cppcx/mapview-first-method.md)|Возвращает итератор, который инициализируется первым элементом в представлении карты.|  
|[Метод MapView::HasKey](../cppcx/mapview-haskey-method.md)|Определяет, содержит ли текущий объект MapView указанный ключ.|  
|[Метод MapView::Lookup](../cppcx/mapview-lookup-method.md)|Извлекает элемент по указанному ключу в текущем объекте MapView.|  
|[Метод MapView::Size](../cppcx/mapview-size-method.md)|Возвращает количество элементов в текущем объекте MapView.|  
|[Метод MapView::Split](../cppcx/mapview-split-method.md)|Разделяет исходный объект MapView на два объекта MapView.|  
  
## Иерархия наследования  
 `MapView`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)