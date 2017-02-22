---
title: "CMFCRibbonStatusBarPane Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCRibbonStatusBarPane"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonStatusBarPane class"
ms.assetid: 5d034c3c-ecca-4267-b88c-0f55a2884dd0
caps.latest.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 33
---
# CMFCRibbonStatusBarPane Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Класс `CMFCRibbonStatusBarPane` реализующий элемент ленты, который можно добавить в строку состояния ленты.  
  
## Синтаксис  
  
```  
class CMFCRibbonStatusBarPane : public CMFCRibbonButton  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane](../Topic/CMFCRibbonStatusBarPane::CMFCRibbonStatusBarPane.md)|Создания и инициализации объект `CMFCRibbonStatusBarPane`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonStatusBarPane::GetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::GetAlmostLargeText.md)|Возвращает строку, которая определяет самую длинную строку текста, которую можно отобразить в области без усечения.|  
|[CMFCRibbonStatusBarPane::GetTextAlign](../Topic/CMFCRibbonStatusBarPane::GetTextAlign.md)|Возвращает текущий параметр выравнивания текста.|  
|[CMFCRibbonStatusBarPane::IsAnimation](../Topic/CMFCRibbonStatusBarPane::IsAnimation.md)|Определяет, является ли анимация выполняется.|  
|[CMFCRibbonStatusBarPane::IsExtended](../Topic/CMFCRibbonStatusBarPane::IsExtended.md)|Определяет, является ли панель найдено в расширенной панели строки состояния ленты.|  
|[CMFCRibbonStatusBarPane::OnDrawBorder](../Topic/CMFCRibbonStatusBarPane::OnDrawBorder.md)|\(Переопределяет [CMFCRibbonButton::OnDrawBorder](../Topic/CMFCRibbonButton::OnDrawBorder.md)\).|  
|[CMFCRibbonStatusBarPane::OnFillBackground](../Topic/CMFCRibbonStatusBarPane::OnFillBackground.md)|\(Переопределяет [CMFCRibbonButton::OnFillBackground](../Topic/CMFCRibbonButton::OnFillBackground.md)\).|  
|[CMFCRibbonStatusBarPane::SetAlmostLargeText](../Topic/CMFCRibbonStatusBarPane::SetAlmostLargeText.md)|Определяет самую длинную строку текста, которую можно отобразить в области без усечения.|  
|[CMFCRibbonStatusBarPane::SetAnimationList](../Topic/CMFCRibbonStatusBarPane::SetAnimationList.md)|Присвоение панели образ список, который может быть использован для анимации.|  
|[CMFCRibbonStatusBarPane::SetTextAlign](../Topic/CMFCRibbonStatusBarPane::SetTextAlign.md)|Задает выравнивание текста.|  
|[CMFCRibbonStatusBarPane::StartAnimation](../Topic/CMFCRibbonStatusBarPane::StartAnimation.md)|Запускает анимацию, присвоена на панели.|  
|[CMFCRibbonStatusBarPane::StopAnimation](../Topic/CMFCRibbonStatusBarPane::StopAnimation.md)|Останавливает анимацию, присвоена на панели.  .|  
  
### Защищенные методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCRibbonStatusBarPane::OnFinishAnimation](../Topic/CMFCRibbonStatusBarPane::OnFinishAnimation.md)|Вызываемый платформой, если анимация, присвоена на панели останавливается.|  
  
## Пример  
 В следующем примере показано, как использовать различные методы класса `CMFCRibbonStatusBarPane`.  Примере показано создание объекта `CMFCRibbonStatusBarPane` присвойте выравнивание текста метки панели строки состояния, указывающее самое длинное текст, который может отображаться на панели строки состояния без усечения, присоединяет к панели строки состояния список образа, который может быть использован для анимации и запускает анимацию.  
  
 [!code-cpp[NVC_MFC_RibbonApp#2](../../mfc/reference/codesnippet/CPP/cmfcribbonstatusbarpane-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonButton](../../mfc/reference/cmfcribbonbutton-class.md)  
  
 [CMFCRibbonStatusBarPane](../../mfc/reference/cmfcribbonstatusbarpane-class.md)  
  
## Требования  
 **заголовок:** afxribbonstatusbarpane.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCRibbonButton Class](../../mfc/reference/cmfcribbonbutton-class.md)   
 [CMFCRibbonStatusBar Class](../../mfc/reference/cmfcribbonstatusbar-class.md)