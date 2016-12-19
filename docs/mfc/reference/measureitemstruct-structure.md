---
title: "Структура MEASUREITEMSTRUCT | Microsoft Docs"
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
  - "MEASUREITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "MEASUREITEMSTRUCT - структура"
ms.assetid: d141ace4-47cb-46b5-a81c-ad2c5e5a8501
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура MEASUREITEMSTRUCT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `MEASUREITEMSTRUCT` уведомляет Windows измерений определяемых пользователем элемента управления или пункта меню.  
  
## Синтаксис  
  
```  
  
      typedef struct tagMEASUREITEMSTRUCT {  
   UINT CtlType;  
   UINT CtlID;  
   UINT itemID;  
   UINT itemWidth;  
   UINT itemHeight;  
   DWORD itemData  
} MEASUREITEMSTRUCT;  
```  
  
#### Параметры  
 `CtlType`  
 Содержит тип элемента управления.  Значения для типов элементов управления следующим образом:  
  
-   Поле со списком рисования владельцем **ODT\_COMBOBOX**  
  
-   Список рисования владельцем **ODT\_LISTBOX**  
  
-   Меню рисования владельцем **ODT\_MENU**  
  
 `CtlID`  
 Содержит идентификатор элемента управления для поля со списком, списке или кнопки.  Этот элемент не используется для меню.  
  
 `itemID`  
 Содержит идентификатор пункта меню для меню или идентификатор элемента список\-окно\- для поля со списком или списка переменной высоты.  Этот элемент не используется для поля со списком или списка фиксированной высоты, или для кнопки.  
  
 *itemWidth*  
 Задает ширину пункта меню.  Владелец пункта меню рисования владельцем должен заполнить этот член до возвращения из сообщения.  
  
 *itemHeight*  
 Задает высоту отдельного элемента в списке или меню.  До возвращения из сообщения, владелец поля со списком, списке или пункта меню рисования владельцем должен заполнять этот член.  Максимальная высота элемента списка 255.  
  
 `itemData`  
 Для поля со списком или списка этот элемент содержит значение, переданные в список одним из следующих:  
  
-   [CComboBox::AddString](../Topic/CComboBox::AddString.md)  
  
-   [CComboBox::InsertString](../Topic/CComboBox::InsertString.md)  
  
-   [CListBox::AddString](../Topic/CListBox::AddString.md)  
  
-   [CListBox::InsertString](../Topic/CListBox::InsertString.md)  
  
 Для меню этот элемент содержит значение, переданные в меню одним из следующих:  
  
-   [CMenu::AppendMenu](../Topic/CMenu::AppendMenu.md)  
  
-   [CMenu::InsertMenu](../Topic/CMenu::InsertMenu.md)  
  
-   [CMenu::ModifyMenu](../Topic/CMenu::ModifyMenu.md)  
  
 Это позволяет Windows к процессу взаимодействия пользователя с элементом управления.  Сбой заполнения правильные члены в структуре `MEASUREITEMSTRUCT` приведет к неверная операция элемента управления.  
  
## Требования  
 **Header:** winuser.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)