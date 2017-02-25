---
title: "CMFCCaptionButton Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCCaptionButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCCaptionButton class"
ms.assetid: c5774b38-c0dd-414a-9ede-3b2f78f233ec
caps.latest.revision: 28
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 30
---
# CMFCCaptionButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCCaptionButton` реализует кнопку, которая отображается в строке заголовка для панели закрепления или окна области.  Обычно платформа создает кнопки заголовка автоматически.  
  
## Синтаксис  
  
```  
class CMFCCaptionButton : public CObject  
```  
  
## Члены  
  
### Конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCCaptionButton::CMFCCaptionButton](../Topic/CMFCCaptionButton::CMFCCaptionButton.md)|Создает объект CMFCCaptionButton.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCCaptionButton::GetHit](../Topic/CMFCCaptionButton::GetHit.md)|Возвращает команду, представленную кнопкой.|  
|[CMFCCaptionButton::GetIconID](../Topic/CMFCCaptionButton::GetIconID.md)|Возвращает идентификатор образа, связанное с кнопкой.|  
|[CMFCCaptionButton::GetRect](../Topic/CMFCCaptionButton::GetRect.md)|Возвращает прямоугольник, занятый кнопкой.|  
|[CMFCCaptionButton::GetSize](../Topic/CMFCCaptionButton::GetSize.md)|Возвращает ширину и высоту кнопки.|  
|[CMFCCaptionButton::IsMiniFrameButton](../Topic/CMFCCaptionButton::IsMiniFrameButton.md)|Указывает, установлена ли высота заголовка окна на мини размера.|  
|[CMFCCaptionButton::Move](../Topic/CMFCCaptionButton::Move.md)|Задает место рисования кнопки показать окна и состояние.|  
|[CMFCCaptionButton::OnDraw](../Topic/CMFCCaptionButton::OnDraw.md)|Рисует кнопку заголовка.|  
|[CMFCCaptionButton::SetMiniFrameButton](../Topic/CMFCCaptionButton::SetMiniFrameButton.md)|Задает мини размер заголовка окна.|  
  
## Заметки  
 Можно создать класс, наследуемый от [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md) и использовать защищенный метод, `AddButton`, чтобы добавить кнопки заголовка к мини фреймовому окно.  
  
 CPaneFrameWnd.h определяет идентификаторы команд для 2 типов кнопки заголовка.  
  
-   `AFX_CAPTION_BTN_PIN`, который отображает кнопку закрепления если панель закрепления поддерживает режим автоматического скрытия.  
  
-   `AFX_CAPTION_BTN_CLOSE`, которая отображает кнопку **Закрыть** если панель можно закрыть или скрыть.  
  
## Пример  
 В следующем примере показано, как создать объект `CMFCCaptionButton` и установить мини размер заголовка окна.  
  
 [!code-cpp[NVC_MFC_RibbonApp#43](../../mfc/reference/codesnippet/CPP/cmfccaptionbutton-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCCaptionButton](../../mfc/reference/cmfccaptionbutton-class.md)  
  
## Требования  
 **заголовок:** afxcaptionbutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CPaneFrameWnd Class](../../mfc/reference/cpaneframewnd-class.md)   
 [CDockablePane Class](../Topic/CDockablePane%20Class.md)