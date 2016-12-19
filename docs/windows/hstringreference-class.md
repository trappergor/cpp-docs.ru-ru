---
title: "Класс HStringReference | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "corewrappers/Microsoft::WRL::Wrappers::HStringReference"
dev_langs: 
  - "C++"
ms.assetid: 9bf823b1-17eb-4ac4-8c5d-27d27c7a4150
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс HStringReference
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет HSTRING, созданный из существующей строки.  
  
## Синтаксис  
  
```cpp  
class HStringReference;  
```  
  
## Примечания  
 Время существования буфера резервного копирования в новом HSTRING не управляется [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  Вызывающий объект выделяет строку источника в кадре стека во избежание выделения памяти для кучи и для исключения риска утечки памяти.  Кроме того, вызывающий объект должен убедиться, что строка источника остается неизменной во время существования подключенного HSTRING.  Для получения дополнительной информации см. [WindowsCreateStringReference function](http://msdn.microsoft.com/ru-ru/0361bb7e-da49-4289-a93e-de7aab8712ac).  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор HStringReference::HStringReference](../windows/hstringreference-hstringreference-constructor.md)|Инициализирует новый экземпляр класса HStringReference.|  
  
### Члены  
  
|Член|Описание|  
|----------|--------------|  
|[Метод HStringReference::CopyTo](../windows/hstringreference-copyto-method.md)|Копирует текущий объект HStringReference в объект HSTRING.|  
|[Метод HStringReference::Get](../windows/hstringreference-get-method.md)|Извлекает значение базового дескриптора HSTRING.|  
  
### Открытые операторы  
  
|Name|Описание|  
|----------|--------------|  
|[Оператор HStringReference::Operator\=](../windows/hstringreference-operator-assign-operator.md)|Перемещает значение другого объекта HStringReference в текущий объект HStringReference.|  
|[Оператор HStringReference::Operator\=\=](../windows/hstringreference-operator-equality-operator.md)|Указывает, действительно ли два параметра равны.|  
|[Оператор HStringReference::O](../windows/hstringreference-operator-inequality-operator.md)|Указывает, действительно ли два параметра не равны.|  
  
## Иерархия наследования  
 `HStringReference`  
  
## Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers  
  
## См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../Topic/Microsoft::WRL::Wrappers%20Namespace.md)