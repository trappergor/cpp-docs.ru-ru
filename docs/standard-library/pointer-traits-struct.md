---
title: "Структура pointer_traits | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "memory/std::pointer_traits::element_type"
  - "memory/std::pointer_traits::pointer"
  - "memory/std::pointer_traits"
  - "memory/std::pointer_traits::difference_type"
  - "memory/std::pointer_traits::rebind"
  - "xmemory0/std::pointer_traits::element_type"
  - "xmemory0/std::pointer_traits::pointer"
  - "xmemory0/std::pointer_traits"
  - "xmemory0/std::pointer_traits::difference_type"
  - "xmemory0/std::pointer_traits::rebind"
dev_langs: 
  - "C++"
ms.assetid: 545aecf1-3561-4859-8b34-603c079fe1b3
caps.latest.revision: 13
caps.handback.revision: 2
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Структура pointer_traits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предоставляет данные, необходимые объекту класса шаблонов `allocator_traits` для описания распределителя с типом указателя `Ptr`.  
  
## Синтаксис  
  
```cpp  
template<class Ptr>  
    struct pointer_traits;  
```  
  
## Заметки  
 PTR может быть сырцовым указателем типа `Ty *` или класса со следующими свойствами.  
  
```  
template<class Ty, class... Rest>  
    struct Ptr  
    { // describes a pointer type usable by allocators  
    typedef Ptr pointer;  
    typedef T1 element_type; // optional  
    typedef T2 difference_type; // optional  
    template<class Other>  
        using rebind = typename Ptr<Other, Rest...>; // optional  
  
    static pointer pointer_to(element_type& obj); // optional  
    };  
```  
  
> [!WARNING]
>  Хотя стандарт C\+\+ определяет члена `rebind` как шаблон псевдонима, Visual C\+\+ реализует rebind как `struct`.  
  
### Определения типов  
  
|Name|Описание|  
|----------|--------------|  
|`typedef T2 difference_type`|Тип `T2``Ptr::difference_type`, если этот тип существует, в противном случае `ptrdiff_t`.  Если `Ptr` необработанный указатель, тип `ptrdiff_t`.|  
|`typedef T1 element_type`|Тип `T1``Ptr::element_type`, если этот тип существует, в противном случае `Ty`.  Если `Ptr` необработанный указатель, тип `Ty`.|  
|`typedef Ptr pointer`|Типом является `Ptr`.|  
  
### структурам;  
  
|Name|Описание|  
|----------|--------------|  
|`pointer_traits::rebind`|Пытается преобразовать базовый тип указателя к указанному типу.|  
  
### Методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод pointer\_traits::pointer\_to](../Topic/pointer_traits::pointer_to%20Method.md)|Преобразование произвольная ссылку на объект класса `Ptr`.|  
  
## Требования  
 **Заголовок:**\<memory\>  
  
 **Пространство имен:** std  
  
## См. также  
 [\<memory\>](../standard-library/memory.md)   
 [Класс allocator\_traits](../Topic/allocator_traits%20Class.md)