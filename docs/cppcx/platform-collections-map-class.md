---
title: "Класс Platform::Collections::Map | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "collection/Platform::Collections::Map"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Map - класс (C++/Cx)"
ms.assetid: 2b8cf968-1167-4898-a149-1195b32c1785
caps.latest.revision: 19
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 19
---
# Класс Platform::Collections::Map
Представляет *сопоставление*, являющееся коллекцией пар "ключ\-значение".  
  
## Синтаксис  
  
```  
template <  
   typename K,  
   typename V,  
   typename C = std::less<K>  
ref class Map sealed;  
```  
  
#### Параметры  
 `K`  
 Тип ключа в паре "ключ\-значение".  
  
 `V`  
 Тип значения в паре "ключ\-значение".  
  
 `C`  
 Тип, предоставляющий объект функции, который может сравнить два значения элементов как ключи сортировки для определения их относительного порядка в объекте Map. По умолчанию [std::less\<K\>](../standard-library/less-struct.md).  
  
 \_\_is\_valid\_winrt\_type\(\)  
 Созданная компилятором функция, которая проверяет тип K и V и предоставляет понятное сообщение об ошибке, если тип невозможно сохранить на карте.  
  
## Заметки  
 Допустимые типы:  
  
-   целые числа  
  
-   класс интерфейса ^  
  
-   открытый класс ссылки ^  
  
-   структура значений  
  
-   открытый класс перечисления  
  
 Карта — это, по сути, программа\-оболочка для [std::map](../standard-library/map-class.md). Это конкретная реализация типов [Windows::Foundation::Collections::IMap\<Windows::Foundation::Collections::IKeyValuePair\<K,V](http://go.microsoft.com/fwlink/p/?LinkId=262408) и [IObservableMap](http://msdn.microsoft.com/library/windows/apps/br226050.aspx), передаваемых по открытым интерфейсам [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)], в C\+\+. При попытке использования типа `Platform::Collections::Map` в открытом возвращаемом значении или параметре возникает ошибка компилятора C3986. Вы можете исправить эту ошибку, изменив тип параметра или возвращаемого значения на [Windows::Foundation::Collections::IMap\<K,V\>](http://go.microsoft.com/fwlink/p/?LinkId=262408).  
  
 Для получения дополнительной информации см. [Коллекции](../cppcx/collections-c-cx.md).  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[Map::Map \- конструктор](../cppcx/map-map-constructor.md)|Инициализирует новый экземпляр класса Map.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод Map::Clear](../cppcx/map-clear-method.md)|Удаляет все пары "ключ\-значение" из текущего объекта Map.|  
|[Метод Map::First](../cppcx/map-first-method.md)|Возвращает итератор, указывающий первый элемент в сопоставлении.|  
|[Метод Map::GetView](../cppcx/map-getview-method.md)|Возвращает представление текущего объекта Map, доступное только для чтения \(т. е. [Класс Platform::Collections::MapView](../cppcx/platform-collections-mapview-class.md)\).|  
|[Метод Map::HasKey](../cppcx/map-haskey-method.md)|Определяет, содержит ли текущий объект Map указанный ключ.|  
|[Метод Map::Insert](../cppcx/map-insert-method.md)|Добавляет в текущий объект Map указанную пару "ключ\-значение".|  
|[Метод Map::Lookup](../cppcx/map-lookup-method.md)|Извлекает элемент по указанному ключу в текущем объекте Map.|  
|[Метод Map::Remove](../cppcx/map-remove-method.md)|Удаляет указанную пару "ключ\-значение" из текущего объекта Map.|  
|[Метод Map::Size](../cppcx/map-size-method.md)|Возвращает количество элементов в текущем объекте Map.|  
  
### События  
  
|||  
|-|-|  
|Имя|Описание|  
|[Событие Map::MapChanged](../cppcx/map-mapchanged-event.md) `event`|Происходит при изменении объекта Map.|  
  
## Иерархия наследования  
 `Map`  
  
## Требования  
 **Заголовок:** collection.h  
  
 **Пространство имен:** Platform::Collections  
  
## См. также  
 [\(NOTINBUILD\) Пространство имен Platform](http://msdn.microsoft.com/ru-ru/f3ce3eab-028c-4204-ba9f-9ab8af17c8c4)   
 [Создание компонентов среды выполнения Windows в C\+\+](http://msdn.microsoft.com/library/5b7251e6-4271-4f13-af80-c1cf5b1489bf)