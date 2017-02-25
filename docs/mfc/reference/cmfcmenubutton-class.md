---
title: "Класс CMFCMenuButton | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCMenuButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Класс CMFCMenuButton"
ms.assetid: 53d3d459-1e5a-47c5-8b7f-2e61f6af5187
caps.latest.revision: 32
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 34
---
# Класс CMFCMenuButton
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Кнопку, которая отображается контекстное меню меню и отчет выделения меню пользователя.  
  
## Синтаксис  
  
```  
class CMFCMenuButton : public CMFCButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMenuButton::CMFCMenuButton](../Topic/CMFCMenuButton::CMFCMenuButton.md)|Создает объект `CMFCMenuButton`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMenuButton::PreTranslateMessage](../Topic/CMFCMenuButton::PreTranslateMessage.md)|Вызывается средой выполнения для перевода окна сообщения перед их передачей.  Переопределения \( `CMFCButton::PreTranslateMessage`\).|  
|[CMFCMenuButton::SizeToContent](../Topic/CMFCMenuButton::SizeToContent.md)|Изменяет размер кнопки в соответствии с его размера текста и изображений.|  
  
### Элементы данных  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCMenuButton::m\_bOSMenu](../Topic/CMFCMenuButton::m_bOSMenu.md)|Указывает, отображать ли контекстное меню меню системы по умолчанию или использовать [CContextMenuManager::TrackPopupMenu](../Topic/CContextMenuManager::TrackPopupMenu.md).|  
|[CMFCMenuButton::m\_bRightArrow](../Topic/CMFCMenuButton::m_bRightArrow.md)|Определяет, отображается ли меню под контекстное меню или справа от кнопки.|  
|[CMFCMenuButton::m\_bStayPressed](../Topic/CMFCMenuButton::m_bStayPressed.md)|Определяет, является ли кнопка меню изменяет ее состояние после выпусков пользователя кнопку.|  
|[CMFCMenuButton::m\_hMenu](../Topic/CMFCMenuButton::m_hMenu.md)|Дескриптор подключенному меню Windows.|  
|[CMFCMenuButton::m\_nMenuResult](../Topic/CMFCMenuButton::m_nMenuResult.md)|Идентификатор, указывающий элемент, выбранный пользователем из контекстного меню меню.|  
  
## Заметки  
 Класс `CMFCMenuButton` является производным от класса [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md), который, в свою очередь, является производным от класса [CButton Class](../../mfc/reference/cbutton-class.md).  Таким образом, можно использовать `CMFCMenuButton` в коде так же, как `CButton`.  
  
 При создании объекта `CMFCMenuButton` необходимо передать в дескриптор, всплывающему меню.  Далее следует использовать функцию `CMFCMenuButton::SizeToContent`.  `CMFCMenuButton::SizeToContent` проверяет, что размер кнопки достаточно для включения стрелки, указывающей на позицию всплывающее окно " \- а именно под или справа от кнопки.  
  
## Пример  
 В следующем примере показано, как задать дескриптор меню вложенного к кнопке, изменить кнопки в соответствии с его текст и обработка размер, и установите контекстное меню меню, которое отображается средой выполнения.  Этот фрагмент кода часть [Пример новых элементов управления](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls#38](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls#39](../../mfc/reference/codesnippet/CPP/cmfcmenubutton-class_2.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CButton](../../mfc/reference/cbutton-class.md)  
  
 [CMFCButton](../../mfc/reference/cmfcbutton-class.md)  
  
 [CMFCMenuButton](../../mfc/reference/cmfcmenubutton-class.md)  
  
## Требования  
 **Заголовок:** afxmenubutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCButton Class](../../mfc/reference/cmfcbutton-class.md)