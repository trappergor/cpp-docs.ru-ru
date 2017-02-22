---
title: "CMFCRibbonSeparator Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "GetThisClass"
  - "CMFCRibbonSeparator::GetThisClass"
  - "CMFCRibbonSeparator.CreateObject"
  - "CMFCRibbonSeparator::CreateObject"
  - "CMFCRibbonSeparator"
  - "CreateObject"
  - "CMFCRibbonSeparator.GetThisClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCRibbonSeparator class"
  - "CreateObject method"
  - "GetThisClass method"
ms.assetid: bedb1a53-cb07-4c3c-be12-698c5409e7cf
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CMFCRibbonSeparator Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Реализует разделитель ленты.  
  
## Синтаксис  
  
```  
class CMFCRibbonSeparator : public CMFCRibbonBaseElement  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::CMFCRibbonSeparator](../Topic/CMFCRibbonSeparator::CMFCRibbonSeparator.md)|Создает объект `CMFCRibbonSeparator`.|  
  
### Открытые методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::AddToListBox](../Topic/CMFCRibbonSeparator::AddToListBox.md)|Добавляет к списку **Команды** разделитель в диалоговом окне **Настроить**.  \(Переопределяет [CMFCRibbonBaseElement::AddToListBox](../Topic/CMFCRibbonBaseElement::AddToListBox.md)\).|  
|`CMFCRibbonSeparator::CreateObject`|Используемый платформой, чтобы создать динамический экземпляр этого типа класса.|  
|`CMFCRibbonSeparator::GetThisClass`|Используемый платформой для получения указателя на объект [CRuntimeClass](../Topic/CRuntimeClass%20Structure.md), который связан с этим типом класса.|  
  
### Защищенные методы  
  
|||  
|-|-|  
|Имя|Описание|  
|[CMFCRibbonSeparator::CopyFrom](../Topic/CMFCRibbonSeparator::CopyFrom.md)|Метод копии, который устанавливает переменные\-члены разделителя из другого объекта.|  
|[CMFCRibbonSeparator::GetRegularSize](../Topic/CMFCRibbonSeparator::GetRegularSize.md)|Возвращает размер разделителя.|  
|[CMFCRibbonSeparator::IsSeparator](../Topic/CMFCRibbonSeparator::IsSeparator.md)|Указывает, является ли это разделитель.|  
|[CMFCRibbonSeparator::IsTabStop](../Topic/CMFCRibbonSeparator::IsTabStop.md)|Указывает, является ли это позиция табуляции.|  
|[CMFCRibbonSeparator::OnDraw](../Topic/CMFCRibbonSeparator::OnDraw.md)|Вызывается системой при рисовании разделителя на ленте или быстрого доступа.|  
|[CMFCRibbonSeparator::OnDrawOnList](../Topic/CMFCRibbonSeparator::OnDrawOnList.md)|Вызывается системой при рисовании разделителя в списке **Команды**.|  
  
## Заметки  
 Разделитель ленты по вертикали или горизонтальная линия, которая логически разделяют элементов ленты.  Разделитель можно нарисовать на элементе управления ленты меню главной программы строке состояния ленты и быстрого доступа.  
  
 Для использования разделителя в приложении создайте новый объект и добавьте его в меню главной программы, как показано ниже:  
  
```  
CMFCRibbonMainPanel* pMainPanel = m_wndRibbonBar.AddMainCategory(_T("Main Menu"), IDB_FILESMALL, IDB_FILELARGE);   
...  
pMainPanel->Add(new CMFCRibbonSeparator(TRUE));  
```  
  
 Вызовите [CMFCRibbonPanel::AddSeparator](../Topic/CMFCRibbonPanel::AddSeparator.md) для добавления разделители панели ленты.  Разделители выделены и добавлены внутренне методом `AddSeparator`.  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CMFCRibbonBaseElement](../../mfc/reference/cmfcribbonbaseelement-class.md)  
  
 [CMFCRibbonSeparator](../../mfc/reference/cmfcribbonseparator-class.md)  
  
## Требования  
 **заголовок:** afxbaseribbonelement.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Классы](../Topic/MFC%20Classes.md)