---
title: "Класс Platform::Collections::UnorderedMap | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::UnorderedMap"
ms.assetid: dc84f261-b13c-4c0a-9b57-30dcb9e3065e
caps.latest.revision: 7
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 7
---
# Класс Platform::Collections::UnorderedMap
Представляет неупорядоченное *сопоставление*, являющееся коллекцией пар "ключ\-значение".  
  
## Синтаксис  
  
```scr  
template <  
   typename K,  
   typename V,  
   typename C = std::equal_to<K>  
>  
ref class Map sealed;  
```  
  
#### Параметры  
 `K`  
 Тип ключа в паре "ключ\-значение".  
  
 `V`  
 Тип значения в паре "ключ\-значение".  
  
 `C`  
 Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию имеет значение [std::equal\_to\<K\>](../standard-library/equal-to-struct.md).  
  
## Заметки  
 Допустимые типы:  
  
-   целые числа  
  
-   класс интерфейса ^  
  
-   открытый класс ссылки ^  
  
-   структура значений  
  
-   открытый класс перечисления  
  
 UnorderedMap является, по существу, программой\-оболочкой для [std::unordered\_map](../standard-library/unordered-map-class.md), которая поддерживает хранение типов [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Это конкретная реализация типов [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408) и [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx), передаваемых через открытые интерфейсы [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. При попытке использования типа Platform::Collections::UnorderedMap в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IMap](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Для получения дополнительной информации см. [Коллекции](../cppcx/collections-c-cx.md).  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|Конструктор UnorderedMap::UnorderedMap|Инициализирует новый экземпляр класса Map.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод UnorderedMap::Clear](../cppcx/unorderedmap-clear-method.md)|Удаляет все пары "ключ\-значение" из текущего объекта Map.|  
|[Метод UnorderedMap::First](../cppcx/unorderedmap-first-method.md)|Возвращает итератор, указывающий первый элемент в сопоставлении.|  
|[Метод UnorderedMap::GetView](../cppcx/unorderedmap-getview-method.md)|Возвращает доступное только для чтения представление текущего сопоставления, то есть класс Platform::Collections::UnorderedMapView.|  
|[Метод UnorderedMap::HasKey](../cppcx/unorderedmap-haskey-method.md)|Определяет, содержит ли текущий объект Map указанный ключ.|  
|[Метод UnorderedMap::Insert](../cppcx/unorderedmap-insert-method.md)|Добавляет в текущий объект Map указанную пару "ключ\-значение".|  
|[Метод UnorderedMap::Lookup](../cppcx/unorderedmap-lookup-method.md)|Извлекает элемент по указанному ключу в текущем объекте Map.|  
|[Метод UnorderedMap::Remove](../cppcx/unorderedmap-remove-method.md)|Удаляет указанную пару "ключ\-значение" из текущего объекта Map.|  
|[Метод UnorderedMap::Size](../cppcx/unorderedmap-size-method.md)|Возвращает количество элементов в текущем объекте Map.|  
  
### События  
  
|||  
|-|-|  
|Имя|Описание|  
|[Событие Map::MapChanged](../cppcx/map-mapchanged-event.md) `event`|Происходит при изменении объекта Map.|  
  
## Иерархия наследования  
 `UnorderedMap`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Пространство имен Platform::Collections](../cppcx/platform-collections-namespace.md)   
 [Класс Platform::Collections::Map](../cppcx/platform-collections-map-class.md)   
 [Класс Platform::Collections::UnorderedMapView](../cppcx/platform-collections-unorderedmapview-class.md)   
 [Коллекции](../cppcx/collections-c-cx.md)   
 [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)