---
title: "CFormView Class | Microsoft Docs"
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
  - "CFormView"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFormView class"
  - "form views"
  - "представления, containing controls"
ms.assetid: a99ec313-36f0-4f28-9d2b-de11de14ac19
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CFormView Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Базовый класс, используемый для представлений формы.  
  
## Синтаксис  
  
```  
class CFormView : public CScrollView  
```  
  
## Участники  
  
### Защищенные конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFormView::CFormView](../Topic/CFormView::CFormView.md)|Создает объект `CFormView`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CFormView::IsInitDlgCompleted](../Topic/CFormView::IsInitDlgCompleted.md)|Используется для синхронизации во время инициализации.|  
  
## Заметки  
 По сути, представление формы — это представление, содержащее элементы управления.  Эти элементы управления располагаются на основе ресурса шаблона диалогового окна.  Используйте `CFormView`, если вы хотите задействовать формы в своем приложении.  Эти представления поддерживают прокрутку, возможность которой обеспечивается с помощью функций класса [CScrollView](../../mfc/reference/cscrollview-class.md).  
  
 При [создании приложений на основе форм](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md) вы можете взять за основу его класса представления класс `CFormView`.  
  
 Кроме того, в приложения на основе представлений документов можно добавлять новые [разделы форм](../Topic/Form%20Views%20\(MFC\).md).  Даже если ваше приложение изначально не поддерживает формы, при вставке новой формы Visual C\+\+ обеспечит их поддержку.  
  
 Приложения на основе форм рекомендуется создавать с помощью мастера приложений MFC и команды Add Class.  Если вам требуется создать приложение на основе форм без использования этих методов, см. раздел [Создание приложений на основе форм](../Topic/Creating%20a%20Forms-Based%20MFC%20Application.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CView](../Topic/CView%20Class.md)  
  
 [CScrollView](../../mfc/reference/cscrollview-class.md)  
  
 `CFormView`  
  
## Требования  
 **Заголовок:** afxext.h  
  
## См. также  
 [Пример MFC: SNAPVW](../../top/visual-cpp-samples.md)   
 [Пример MFC: VIEWEX](../../top/visual-cpp-samples.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)   
 [CScrollView Class](../../mfc/reference/cscrollview-class.md)   
 [CView::OnUpdate](../Topic/CView::OnUpdate.md)   
 [CView::OnInitialUpdate](../Topic/CView::OnInitialUpdate.md)   
 [CView::OnPrint](../Topic/CView::OnPrint.md)   
 [CWnd::UpdateData](../Topic/CWnd::UpdateData.md)   
 [CScrollView::ResizeParentToFit](../Topic/CScrollView::ResizeParentToFit.md)