---
title: "CComControl Class | Microsoft Docs"
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
  - "CComControl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ambient properties"
  - "CComControl class"
  - "CComControlBase class, CComControl class"
  - "control flags"
  - "элементы управления [ATL], control helper functions"
  - "элементы управления [ATL], свойства"
  - "свойства хранения, ATL - библиотека"
ms.assetid: 55368c27-bd16-45a7-b701-edb36157c8e8
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComControl Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Этот класс содержит методы для создания и управления управления библиотеки ATL.  
  
> [!IMPORTANT]
>  Этот класс и его члены нельзя использовать в приложениях, выполняемых в этой среде выполнения Windows.  
  
## Синтаксис  
  
```  
  
      template <  
class T,  
class WinBase= CWindowImpl< T>   
>  
class ATL_NO_VTABLE CComControl :  
public CComControlBase, public WinBase;  
```  
  
#### Параметры  
 `T`  
 Класс, реализующий элемент управления.  
  
 *WinBase*  
 Базовый класс для функции над окнами инструментов.  Значения по умолчанию [CWindowImpl](../Topic/CWindowImpl%20Class.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComControl::CComControl](../Topic/CComControl::CComControl.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CComControl::ControlQueryInterface](../Topic/CComControl::ControlQueryInterface.md)|Извлекает указатель на запрашиваемый интерфейс.|  
|[CComControl::CreateControlWindow](../Topic/CComControl::CreateControlWindow.md)|Создает окно для элемента управления.|  
|[CComControl::FireOnChanged](../Topic/CComControl::FireOnChanged.md)|Уведомляет приемник контейнера, что свойство элемента управления изменилось.|  
|[CComControl::FireOnRequestEdit](../Topic/CComControl::FireOnRequestEdit.md)|Уведомляет приемник контейнера, что свойство элемента управления изменением, а объект запрашивает как осуществляются приемников.|  
|[CComControl::MessageBox](../Topic/CComControl::MessageBox.md)|Вызывайте этот метод для создания, отображения и работать с окно сообщения.|  
  
## Заметки  
 `CComControl` набор полезных функций поддержки элемента управления и необходимых элементов данных для элементов управления библиотеки ATL.  При создании стандартный элемент управления или элемент управления DHTML с помощью мастера управления библиотеки ATL мастер автоматически создаваемый класс был производным из `CComControl`.  `CComControl` наследуется большинство методов из [CComControlBase](../Topic/CComControlBase%20Class.md).  
  
 Дополнительные сведения о создании элемента управления см. в разделе [Учебник по библиотеке ATL](../Topic/Active%20Template%20Library%20\(ATL\)%20Tutorial.md).  Дополнительные сведения о мастере проекта библиотеки ATL см. в статье [Создание проекта библиотеки ATL](../../atl/reference/creating-an-atl-project.md).  
  
 Для демонстрации методов и элементов данных `CComControl` см. в разделе пример [CIRC](../../top/visual-cpp-samples.md).  
  
## Иерархия наследования  
 `WinBase`  
  
 [CComControlBase](../Topic/CComControlBase%20Class.md)  
  
 `CComControl`  
  
## Требования  
 **Header:**  atlctl.h  
  
## См. также  
 [CWindowImpl Class](../Topic/CWindowImpl%20Class.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComControlBase Class](../Topic/CComControlBase%20Class.md)   
 [CComCompositeControl Class](../../atl/reference/ccomcompositecontrol-class.md)