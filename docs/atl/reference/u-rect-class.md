---
title: "_U_RECT Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "ATL::_U_RECT"
  - "_U_RECT"
  - "ATL._U_RECT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_RECT class"
  - "U_RECT class"
ms.assetid: 5f880a2d-09cf-4327-bf32-a3519c4dcd63
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_RECT Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс адаптера аргумента позволяет или указатели или ссылки `RECT`, передаваемые функции, которая реализуется в виде указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class _U_RECT  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_RECT::\_U\_RECT](../Topic/_U_RECT::_U_RECT.md)|Конструктор.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_RECT::m\_lpRect](../Topic/_U_RECT::m_lpRect.md)|Указатель на `RECT`.|  
  
## Заметки  
 Класс определяет 2 перегруженные варианты конструктора: принять аргумент **RECT&**, а второй принимает аргумент `LPRECT`.  Первый конструктор хранит адрес аргумента ссылки в элементе данных одного типа, [m\_lpRect](../Topic/_U_RECT::m_lpRect.md).  Аргумент конструктора указателя хранятся непосредственно без преобразования.  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)