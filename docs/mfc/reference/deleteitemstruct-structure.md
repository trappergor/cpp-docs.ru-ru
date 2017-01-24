---
title: "Структура DELETEITEMSTRUCT | Microsoft Docs"
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
  - "DELETEITEMSTRUCT"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DELETEITEMSTRUCT - структура"
ms.assetid: 48d3998c-f4a8-402a-bf90-df3770a78685
caps.latest.revision: 13
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура DELETEITEMSTRUCT
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Структура `DELETEITEMSTRUCT` описывает удаленный определяемый пользователем элемент списка или поля со списком.  
  
## Синтаксис  
  
```  
  
      typedef struct tagDELETEITEMSTRUCT { /* ditms */  
    UINT CtlType;  
    UINT CtlID;  
    UINT itemID;  
    HWND hwndItem;  
    UINT itemData;  
} DELETEITEMSTRUCT;  
```  
  
#### Параметры  
 `CtlType`  
 Определяет **ODT\_LISTBOX** \(определенный пользователем список\) или **ODT\_COMBOBOX** \(определяемое пользователем полей со списком\).  
  
 `CtlID`  
 Задает идентификатор списка или поля со списком.  
  
 `itemID`  
 Определяет индекс элемента, удаленных в список или поле со списком.  
  
 `hwndItem`  
 Идентифицирует элемент управления.  
  
 `itemData`  
 Указывает приложения, данные для элемента.  Это значение передается элементу управления в параметре **LPARAM** сообщения, которое добавляет элемент в список или поле со списком.  
  
## Заметки  
 При удалении элемента из списка или поля со списком или когда удаляется списка или поля со списком, Windows отправляет сообщение `WM_DELETEITEM` к владельцу для каждого удаленного элемента.  Параметр **LPARAM** сообщения содержит указатель на этой структуре.  
  
## Требования  
 **Заголовок:** atldbcli.h  
  
## См. также  
 [Структуры, стили, обратные вызовы и схемы сообщений](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)