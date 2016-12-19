---
title: "initializer_list Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 1f2c0ff4-5636-4f79-b008-e75426e3d2ab
caps.latest.revision: 17
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# initializer_list Class
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предоставляет доступ к массиву элементов, в котором каждый элемент имеет указанный тип.  
  
## Синтаксис  
  
```cpp  
template<  
    class Type >  
    class initializer_list  
```  
  
#### Параметры  
  
|Параметр|Описание|  
|--------------|--------------|  
|`_Elem`|Тип данных элемента для сохранения в `initializer_list`.|  
|`_First`|Указатель на первый элемент `initializer_list`.|  
|`_Last`|Указатель на последний элемент `initializer_list`.|  
  
## Заметки  
 `initializer_list` можно создать при помощи списка заключенного в фигурные скобки инициализатора:  
  
```cpp  
initializer_list<int> i1{ 1, 2, 3, 4 };  
```  
  
 компилятор преобразует списки заключенного в фигурные скобки инициализатора с однородными элементами в `initializer_list` каждый раз, когда сигнатуре функции требуется `initializer_list`.  Дополнительные сведения об использовании `initializer_list` см. в разделе [Единообразная инициализация и делегирование конструкторов](../cpp/uniform-initialization-and-delegating-constructors.md).  
  
### Конструкторы  
  
|||  
|-|-|  
|[initializer\_list](../Topic/forward_list::forward_list.md)|Создает объект типа `initializer_list`.|  
  
### Typedefs  
  
|||  
|-|-|  
|value\_type|Тип элементов в `initializer_list`.|  
|ссылка|Тип, предоставляющий ссылку на элемент в `initializer_list`.|  
|const\_reference|Тип, предоставляющий постоянную ссылку на элемент в `initializer_list`.|  
|size\_type|Тип, представляющий количество элементов в `initializer_list`.|  
|iterator|Тип, предоставляющий итератор для `initializer_list`.|  
|const\_iterator|Тип, предоставляющий постоянный итератор для `initializer_list`.|  
  
### Функции\-члены  
  
|||  
|-|-|  
|[begin](../Topic/initializer_list::begin.md)|Возвращает указатель на первый элемент в `initializer_list`.|  
|[end](../Topic/initializer_list::end.md)|Возвращает указатель на позицию, следующую за последним элементом в `initializer_list`.|  
|[size](../Topic/initializer_list::size.md)|Возвращает количество элементов в контейнере `initializer_list`.|  
  
## Требования  
 **Заголовок:** \<initializer\_list\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<forward\_list\>](../standard-library/forward-list.md)