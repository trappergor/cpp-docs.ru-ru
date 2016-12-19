---
title: "Класс CMFCDynamicLayout | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
dev_langs: 
  - "C++"
ms.assetid: c2df2976-f049-47fc-9cf0-abe3e01948bc
caps.latest.revision: 16
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс CMFCDynamicLayout
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Определяет порядок перемещения и изменения размеров элементов управления при изменении размеров окна.  
  
## Синтаксис  
  
```  
class CMFCDynamicLayout : public CObject  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|`CMFCDynamicLayout::CMFCDynamicLayout`|Создает объект `CMFCDynamicLayout`.|  
|`CMFCDynamicLayout::~CMFCDynamicLayout`|Деструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCDynamicLayout::AddItem](../Topic/CMFCDynamicLayout::AddItem.md)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно \(обычно элемент управления\).|  
|[CMFCDynamicLayout::Adjust](../Topic/CMFCDynamicLayout::Adjust.md)|Добавляет в список окон, управляемых диспетчером динамического макета, дочернее окно \(обычно элемент управления\).|  
|[CMFCDynamicLayout::Create](../Topic/CMFCDynamicLayout::Create.md)|Хранит и проверяет главное окно.|  
|[CMFCDynamicLayout::GetHostWnd](../Topic/CMFCDynamicLayout::GetHostWnd.md)|Возвращает указатель на главное окно.|  
|[CMFCDynamicLayout::GetMinSize](../Topic/CMFCDynamicLayout::GetMinSize.md)|Возвращает минимальный размер окна для макета.|  
|[CMFCDynamicLayout::GetWindowRect](../Topic/CMFCDynamicLayout::GetWindowRect.md)|Извлекает прямоугольник для текущей клиентской области окна.|  
|[CMFCDynamicLayout::HasItem](../Topic/CMFCDynamicLayout::HasItem.md)|Проверяет, добавлялся ли дочерний элемент управления в динамический макет.|  
|[CMFCDynamicLayout::IsEmpty](../Topic/CMFCDynamicLayout::IsEmpty.md)|Проверяет, что в динамический макет не добавлялись дочерние окна.|  
|[CMFCDynamicLayout::LoadResource](../Topic/CMFCDynamicLayout::LoadResource.md)|Считывает динамический макет из ресурса AFX\_DIALOG\_LAYOUT и применяет его для главного окна.|  
|[CMFCDynamicLayout::MoveHorizontal](../Topic/CMFCDynamicLayout::MoveHorizontal.md) \(статический\)|Получает значение [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md), определяющее расстояние, на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.|  
|[CMFCDynamicLayout::MoveHorizontalAndVertical](../Topic/CMFCDynamicLayout::MoveHorizontalAndVertical.md) \(статический\)|Получает значение [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md), определяющее расстояние, на которое дочерний элемент управления будет перемещаться по горизонтали при изменении пользователем размера главного окна.|  
|[CMFCDynamicLayout::MoveNone](../Topic/CMFCDynamicLayout::MoveNone.md) \(статический\)|Получает значение [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md), соответствующее нулевому перемещению дочернего элемента управления по вертикали или горизонтали.|  
|[CMFCDynamicLayout::MoveVertical](../Topic/CMFCDynamicLayout::MoveVertical.md) \(статический\)|Получает значение [MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md), определяющее расстояние, на которое дочерний элемент управления будет перемещаться по вертикали при изменении размера главного окна.|  
|[CMFCDynamicLayout::SetMinSize](../Topic/CMFCDynamicLayout::SetMinSize.md)|Задает минимальный размер окна для макета.|  
|[CMFCDynamicLayout::SizeHorizontal](../Topic/CMFCDynamicLayout::SizeHorizontal.md) \(статический\)|Получает значение [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md), определяющее, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера его главного окна.|  
|[CMFCDynamicLayout::SizeHorizontalAndVertical](../Topic/CMFCDynamicLayout::SizeHorizontalAndVertical.md) \(статический\)|Получает значение [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md), определяющее, как будет меняться размер дочернего элемента управления по горизонтали при изменении пользователем размера его главного окна.|  
|[CMFCDynamicLayout::SizeNone](../Topic/CMFCDynamicLayout::SizeNone.md) \(статический\)|Получает значение [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md), соответствующее нулевому изменению размера дочернего элемента управления.|  
|[CMFCDynamicLayout::SizeVertical](../Topic/CMFCDynamicLayout::SizeVertical.md) \(статический\)|Получает значение [SizeSettings](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md), определяющее, как будет меняться размер дочернего элемента управления по вертикали при изменении размера его главного окна.|  
  
## Вложенные типы  
  
|Имя|Описание|  
|---------|--------------|  
|[Структура CMFCDynamicLayout::MoveSettings](../Topic/CMFCDynamicLayout::MoveSettings%20Structure.md)|Инкапсулирует данные перемещения для элементов управления в динамическом макете.|  
|[CMFCDynamicLayout::SizeSettings Structure](../Topic/CMFCDynamicLayout::SizeSettings%20Structure.md)|Инкапсулирует данные об изменении размера элементов управления в динамическом макете.|  
  
## Заметки  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCDynamicLayout](../../mfc/reference/cmfctoolbarbutton-class.md)  
  
## Требования  
 **Заголовок:** afxlayout.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)