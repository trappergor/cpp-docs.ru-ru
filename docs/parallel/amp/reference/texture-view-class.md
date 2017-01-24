---
title: "Класс texture_view | Microsoft Docs"
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
ms.assetid: 6ec2e289-1626-4727-9592-07981cf1d27d
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс texture_view
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Предоставляет доступ на чтение и запись в текстуре.  `texture_view` может использоваться только для чтения текстур, тип значений которых — `int`, `unsigned int` или `float` с 32\-разрядным bpse по умолчанию.  Для чтения других форматов текстур используйте `texture_view<const _Value_type, _Rank>`.  
  
## Синтаксис  
  
```  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view : public details::_Texture_base<_Value_type, _Rank>;  
  
template <  
   typename _Value_type,  
   int _Rank  
>  
class texture_view<const _Value_type, _Rank> : public details::_Texture_base<_Value_type, _Rank>;  
```  
  
#### Параметры  
 `_Value_type`  
 Тип элементов в агрегате текстур.  
  
 `_Rank`  
 Ранг объекта `texture_view`.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Name|Описание|  
|----------|--------------|  
|`value_type`|Тип элементов в агрегатах текстур.|  
|`coordinates_type`|Тип координаты, используемой для определения текселя в `texture_view`, т е `short_vector` с тем же ранжированием, связанной текстурой, которая имеет тип значения `float`.|  
|`gather_return_type`|Возвращаемый тип, используемый для сбора операция\-, ранжирование 4 `short_vector`, которое содержит 4 однородных компонента цвета собранные от 4 попробованных значений texel.|  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор texture\_view::texture\_view](../Topic/texture_view::texture_view%20Constructor.md)|Перегружен.  Создает экземпляр `texture_view`.|  
|[Деструктор texture\_view::~texture\_view](../Topic/texture_view::~texture_view%20Destructor.md)|Уничтожает экземпляр `texture_view`.|  
  
### Открытые методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод texture\_view::gather\_alpha](../Topic/texture_view::gather_alpha%20Method.md)|Перегружен.  Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает альфа\-компоненты \(w\) 4 выборочных текселей|  
|[Метод texture\_view::gather\_blue](../Topic/texture_view::gather_blue%20Method.md)|Перегружен.  Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает синие компоненты \(z\) 4 выборочных текселей|  
|[Метод texture\_view::gather\_green](../Topic/texture_view::gather_green%20Method.md)|Перегружен.  Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает зеленые компоненты \(y\) 4 выборочных текселей|  
|[Метод texture\_view::gather\_red](../Topic/texture_view::gather_red%20Method.md)|Перегружен.  Создает пример текстуры в заданных координатах с помощью определенной конфигурации выборки и возвращает красные компоненты \(x\) 4 выборочных текселей|  
|[Метод texture\_view::get](../Topic/texture_view::get%20Method.md)|Перегружен.  Получает значение элемента по индексу.|  
|[Метод texture\_view::sample](../Topic/texture_view::sample%20Method.md)|Перегружен.  Создает пример текстуры в заданных координатах и на уровне детализации с помощью определенной конфигурации выборки.|  
|[Метод texture\_view::set](../Topic/texture_view::set%20Method.md)|Устанавливает значение для элемента по индексу.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор texture\_view::operator\(\)](../Topic/texture_view::operator\(\)%20Operator.md)|Перегружен.  Получает значение элемента по индексу.|  
|[texture\_view::operatorOperator](../Topic/texture_view::operatorOperator.md)|Перегружен.  Получает значение элемента по индексу.|  
|[Оператор texture\_view::operator\=](../Topic/texture_view::operator=%20Operator.md)|Перегружен.  Оператор присваивания.|  
  
### Открытые члены данных  
  
|Name|Описание|  
|----------|--------------|  
|[Элемент данных texture\_view::value\_type](../Topic/texture_view::value_type%20Data%20Member.md)|Тип значения элементов `texture_view`.|  
  
## Иерархия наследования  
 `_Texture_base`  
  
 `texture_view`  
  
## Требования  
 **Заголовок:** amp\_graphics.h  
  
 **Пространство имен:** concurrency::graphics  
  
## См. также  
 [Пространство имен Concurrency::graphics](../../../parallel/amp/reference/concurrency-graphics-namespace.md)