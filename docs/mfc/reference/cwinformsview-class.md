---
title: "CWinFormsView Class | Microsoft Docs"
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
  - "CWinFormsView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CWinFormsView class"
  - "MFC [C++], поддержка Windows Forms"
  - "Windows Forms [C++], поддержка MFC"
ms.assetid: d597e397-6529-469b-88f5-7f65a6b9e895
caps.latest.revision: 26
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CWinFormsView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет универсальную функцию для размещения элементов управления Windows Forms в качестве представления MFC.  
  
## Синтаксис  
  
```  
class CWinFormsView : public CView;  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinFormsView::CWinFormsView](../Topic/CWinFormsView::CWinFormsView.md)|Создает объект `CWinFormsView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CWinFormsView::GetControl](../Topic/CWinFormsView::GetControl.md)|Извлекает указатель к элементу управления Windows Forms.|  
  
### Открытые операторы  
  
|Имя||  
|---------|-|  
|[CWinFormsView::operator Control^](../Topic/CWinFormsView::operator%20Control%5E.md)|Приводит тип как указатель к элементу управления Windows Forms.|  
  
## Заметки  
 MFC использует класс `CWinFormsView` для платформы .NET Framework размещение элемента управления Windows Forms в пределах представления MFC.  Элемент управления дочерний элемент собственного представления и занимает всю клиентскую область представления MFC.  Результат аналогичен представление `CFormView`, что позволяет воспользоваться преимуществами конструктора и времени выполнения Windows Forms создание представлений на основе форма\- предикаты и функции.  
  
 Дополнительные сведения об использовании Windows Forms см. в разделе [Использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
> [!NOTE]
>  Интеграция MFC Windows Forms работает только в проектах, которые динамически связываются с MFC \(проектами, в которых определена AFXDLL\).  
  
> [!NOTE]
>  CWinFormsView не поддерживает окно\-разделитель MFC \([CSplitterWnd Class](../../mfc/reference/csplitterwnd-class.md)\).  В настоящее время только элемент управления Splitter \(Windows Forms\)<xref:System.Windows.Forms.Splitter> поддерживается.  
  
## Требования  
 **заголовок:** afxwinforms.h  
  
## См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CWinFormsControl Class](../../mfc/reference/cwinformscontrol-class.md)   
 [CWinFormsDialog Class](../Topic/CWinFormsDialog%20Class.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)