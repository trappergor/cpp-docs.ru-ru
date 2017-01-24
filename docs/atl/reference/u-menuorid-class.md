---
title: "_U_MENUorID Class | Microsoft Docs"
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
  - "ATL._U_MENUorID"
  - "ATL::_U_MENUorID"
  - "_U_MENUorID"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_U_MENUorID class"
  - "U_MENUorID class"
ms.assetid: cfc8032b-61b4-4a68-ba3a-92b82500ccae
caps.latest.revision: 20
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# _U_MENUorID Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс предоставляет программы\-оболочки для **CreateWindow** и **CreateWindowEx**.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
class _U_MENUorID  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_MENUorID::\_U\_MENUorID](../Topic/_U_MENUorID::_U_MENUorID.md)|Конструктор.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[\_U\_MENUorID::m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md)|Дескриптор меню.|  
  
## Заметки  
 Этот класс адаптера аргумента, позволяет **UINT** или идентификаторы \(s\) или дескрипторы меню \(`HMENU` s\), передаваемые функции без необходимости явного приведения на части вызывающего объекта.  
  
 Этот класс предназначен для реализации программы\-оболочки к функциям API, в частности [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) и [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680) Windows, оба они принимают аргумент `HMENU`, который может быть идентификатором дочернего окна \(**UINT**\), а не дескриптор меню.  Например, можно просмотреть этот класс используется как параметр в [CWindowImpl::Create](../Topic/CWindowImpl::Create.md).  
  
 Класс определяет 2 перегруженные варианты конструктора: принять аргумент **UINT**, а второй принимает аргумент `HMENU`.  Аргумент **UINT** просто привести к `HMENU` в конструкторе, и результат, хранящиеся в элементе данных одного типа, [m\_hMenu](../Topic/_U_MENUorID::m_hMenu.md).  Аргумент конструктора `HMENU` хранятся непосредственно без преобразования.  
  
## Требования  
 **Header:**  atlwin.h  
  
## См. также  
 [Class Overview](../../atl/atl-class-overview.md)