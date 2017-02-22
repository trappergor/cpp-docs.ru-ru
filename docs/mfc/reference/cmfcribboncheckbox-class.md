---
title: "CMFCRibbonCheckBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonCheckBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonCheckBox class"
ms.assetid: 3a6c3891-c8d1-4af0-b954-7b9ab048782a
caps.latest.revision: 30
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 32
---
# CMFCRibbonCheckBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonCheckBox` реализует флажок, который можно добавить на панель ленты, панель быстрого доступа или во всплывающее меню.  
  
## Синтаксис  
  
```  
class CMFCRibbonCheckBox : public CMFCRibbonButton  
```  
  
## Участники  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonCheckBox::CMFCRibbonCheckBox](../Topic/CMFCRibbonCheckBox::CMFCRibbonCheckBox.md)|Конструктор.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonCheckBox::GetCompactSize](../Topic/CMFCRibbonCheckBox::GetCompactSize.md)|\(Переопределяет метод [CMFCRibbonButton::GetCompactSize](../Topic/CMFCRibbonButton::GetCompactSize.md).\)|  
|[CMFCRibbonCheckBox::GetIntermediateSize](../Topic/CMFCRibbonCheckBox::GetIntermediateSize.md)|\(Переопределяет метод [CMFCRibbonButton::GetIntermediateSize](../Topic/CMFCRibbonButton::GetIntermediateSize.md).\)|  
|[CMFCRibbonCheckBox::GetRegularSize](../Topic/CMFCRibbonCheckBox::GetRegularSize.md)|\(Переопределяет метод [CMFCRibbonButton::GetRegularSize](../Topic/CMFCRibbonButton::GetRegularSize.md).\)|  
|[CMFCRibbonCheckBox::IsDrawTooltipImage](../Topic/CMFCRibbonCheckBox::IsDrawTooltipImage.md)|\(Переопределяет метод `CMFCRibbonButton::IsDrawTooltipImage`.\)|  
|[CMFCRibbonCheckBox::OnDraw](../Topic/CMFCRibbonCheckBox::OnDraw.md)|\(Переопределяет метод [CMFCRibbonButton::OnDraw](../Topic/CMFCRibbonButton::OnDraw.md).\)|  
|[CMFCRibbonCheckBox::OnDrawMenuImage](../Topic/CMFCRibbonCheckBox::OnDrawMenuImage.md)|\(Переопределяет метод [CMFCRibbonBaseElement::OnDrawMenuImage](../Topic/CMFCRibbonBaseElement::OnDrawMenuImage.md).\)|  
|[CMFCRibbonCheckBox::OnDrawOnList](../Topic/CMFCRibbonCheckBox::OnDrawOnList.md)|\(Переопределяет метод `CMFCRibbonButton::OnDrawOnList`.\)|  
|[CMFCRibbonCheckBox::SetACCData](../Topic/CMFCRibbonCheckBox::SetACCData.md)|\(Переопределяет метод [CMFCRibbonButton::SetACCData](../Topic/CMFCRibbonButton::SetACCData.md).\)|  
  
## Заметки  
 Чтобы использовать класс `CMFCRibbonCheckBox` в вашем приложении, добавьте в код следующий конструктор:  
  
```  
CMFCRibbonCheckBox (UINT nID, LPCTSTR lpszText)  
```  
  
 где `nID` — идентификатор команды флажка, `lpszText` — текстовая метка флажка.  
  
 Чтобы добавить флажок на панель ленты, используйте метод [CMFCRibbonPanel::Add](../Topic/CMFCRibbonPanel::Add.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonCheckBox](../../mfc/reference/cmfcribboncheckbox-class.md)  
  
## Требования  
 **Заголовок:** afxribboncheckbox.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonPanel Class](../../mfc/reference/cmfcribbonpanel-class.md)