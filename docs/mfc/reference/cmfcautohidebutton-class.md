---
title: "CMFCAutoHideButton Class | Microsoft Docs"
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
  - "CMFCAutoHideButton"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCAutoHideButton class"
ms.assetid: c80e6b8b-25ca-4d12-9d27-457731028ab0
caps.latest.revision: 33
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCAutoHideButton Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Кнопка, отображающая или скрывающая [CDockablePane Class](../Topic/CDockablePane%20Class.md), настроенный на скрытие.  
  
## Синтаксис  
  
```  
class CMFCAutoHideButton : public CObject  
```  
  
## Участники  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CMFCAutoHideButton::BringToTop](../Topic/CMFCAutoHideButton::BringToTop.md)||  
|[CMFCAutoHideButton::Create](../Topic/CMFCAutoHideButton::Create.md)|Создает и инициализирует кнопку автоматического скрытия.|  
|[CMFCAutoHideButton::GetAlignment](../Topic/CMFCAutoHideButton::GetAlignment.md)|Извлекает выравнивание кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::GetAutoHideWindow](../Topic/CMFCAutoHideButton::GetAutoHideWindow.md)|Возвращает объект [CDockablePane](../Topic/CDockablePane%20Class.md), связанный с кнопкой автоматического скрытия.|  
|[CMFCAutoHideButton::GetParentToolBar](../Topic/CMFCAutoHideButton::GetParentToolBar.md)||  
|[CMFCAutoHideButton::GetRect](../Topic/CMFCAutoHideButton::GetRect.md)||  
|[CMFCAutoHideButton::GetSize](../Topic/CMFCAutoHideButton::GetSize.md)|Определяет размер кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::GetTextSize](../Topic/CMFCAutoHideButton::GetTextSize.md)|Возвращает размер текстовой метки для кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::HighlightButton](../Topic/CMFCAutoHideButton::HighlightButton.md)|Выделяет кнопку автоматического скрытия.|  
|[CMFCAutoHideButton::IsActive](../Topic/CMFCAutoHideButton::IsActive.md)|Указывает, активна ли кнопка автоматического скрытия.|  
|[CMFCAutoHideButton::IsHighlighted](../Topic/CMFCAutoHideButton::IsHighlighted.md)|Возвращает выделенное состояние кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::IsHorizontal](../Topic/CMFCAutoHideButton::IsHorizontal.md)|Определяет, является кнопка автоматического скрытия горизонтальной или вертикальной.|  
|[CMFCAutoHideButton::IsTop](../Topic/CMFCAutoHideButton::IsTop.md)||  
|[CMFCAutoHideButton::IsVisible](../Topic/CMFCAutoHideButton::IsVisible.md)|Указывает, является ли кнопка видимой.|  
|[CMFCAutoHideButton::Move](../Topic/CMFCAutoHideButton::Move.md)||  
|[CMFCAutoHideButton::OnDraw](../Topic/CMFCAutoHideButton::OnDraw.md)|Этот метод вызывается платформой при рисовании кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::OnDrawBorder](../Topic/CMFCAutoHideButton::OnDrawBorder.md)|Этот метод вызывается платформой при рисовании границ кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::OnFillBackground](../Topic/CMFCAutoHideButton::OnFillBackground.md)|Этот метод вызывается платформой при заливке фона кнопки автоматического скрытия.|  
|[CMFCAutoHideButton::ReplacePane](../Topic/CMFCAutoHideButton::ReplacePane.md)||  
|[CMFCAutoHideButton::ShowAttachedWindow](../Topic/CMFCAutoHideButton::ShowAttachedWindow.md)|Показывает или скрывает связанный [CDockablePane Class](../Topic/CDockablePane%20Class.md).|  
|[CMFCAutoHideButton::ShowButton](../Topic/CMFCAutoHideButton::ShowButton.md)|Показывает или скрывает кнопку автоматического скрытия.|  
|[CMFCAutoHideButton::UnSetAutoHideMode](../Topic/CMFCAutoHideButton::UnSetAutoHideMode.md)||  
  
## Заметки  
 Объект `CMFCAutoHideButton` при создании присоединяется к [CDockablePane Class](../Topic/CDockablePane%20Class.md).  В результате взаимодействия пользователя с объектом `CMFCAutoHideButton` показывается или скрывается объект `CDockablePane`.  
  
 По умолчанию при включении автоматического скрытия платформа автоматически создает объект класса `CMFCAutoHideButton`.  Вместо объекта класса `CMFCAutoHideButton` платформа может создавать элемент настраиваемого класса пользовательского интерфейса.  Чтобы указать, какой настраиваемый класс пользовательского интерфейса должна использовать платформа, задайте для статической переменной\-члена `CMFCAutoHideBar::m_pAutoHideButtonRTS` значение, равное необходимому настраиваемому классу.  Значение этой переменной по умолчанию — `CMFCAutoHideButton`.  
  
## Пример  
 В этом примере демонстрируется создание объекта `CMFCAutoHideButton` и использование различных методов класса `CMFCAutoHideButton`.  В этом примере демонстрируется инициализация объекта `CMFCAutoHideButton` с помощью метода `Create`, а также отображение связанного класса `CDockablePane` и кнопки автоматического скрытия.  
  
 [!code-cpp[NVC_MFC_RibbonApp#32](../../mfc/reference/codesnippet/CPP/cmfcautohidebutton-class_1.cpp)]  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCAutoHideButton](../../mfc/reference/cmfcautohidebutton-class.md)  
  
## Требования  
 **Заголовок:** afxautohidebutton.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)   
 [CMFCAutoHideBar Class](../Topic/CMFCAutoHideBar%20Class.md)   
 [CAutoHideDockSite Class](../../mfc/reference/cautohidedocksite-class.md)