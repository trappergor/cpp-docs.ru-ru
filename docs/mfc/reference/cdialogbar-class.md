---
title: "CDialogBar Class | Microsoft Docs"
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
  - "CDialogBar"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDialogBar class"
  - "dialog bars, Windows modeless dialog box"
  - "диалоговые окна, безрежимные"
ms.assetid: da2f7a30-970c-44e3-87f0-6094bd002cab
caps.latest.revision: 23
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDialogBar Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Предоставляет функциональность немодального диалогового окна Windows на панели элементов управления.  
  
## Синтаксис  
  
```  
class CDialogBar : public CControlBar  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDialogBar::CDialogBar](../Topic/CDialogBar::CDialogBar.md)|Создает объект `CDialogBar`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[CDialogBar::Create](../Topic/CDialogBar::Create.md)|Создает диалоговая панель Windows и вложение его к объекту `CDialogBar`.|  
  
## Заметки  
 Диалоговая панель напоминает диалоговое окно в том, что он содержит стандартные элементы управления Windows, которые пользователь может нашить.  Другое подобие, что будет создан шаблон диалогового окна для представления диалоговую панель.  
  
 Создание и использование диалоговая панель аналогичны созданию и использованию объект `CFormView`.  Во\-первых, используйте [редактор диалоговых окон](../../mfc/dialog-editor.md) для указания шаблона диалогового окна с учетом **WS\_CHILD** и без другой стиль.  Шаблон не должен иметь стиль **WS\_VISIBLE**.  В коде приложения, вызовите конструктор для создания объекта `CDialogBar`, а затем вызовите **Создать** для создания окна диалоговой панели и вложить его к объекту `CDialogBar`.  
  
 Дополнительные сведения о `CDialogBar` см. в статье [диалоговые панели](../../mfc/dialog-bars.md) и [Техническая примечание 31](../../mfc/tn031-control-bars.md), области элементов управления.  
  
> [!NOTE]
>  В текущем выпуске объект `CDialogBar` не может размещение элемента управления Windows Forms.  Дополнительные сведения об элементах управления Windows Forms в Visual C\+\+ см. в разделе [Использование пользовательского элемента управления формы Windows Form в MFC](../../dotnet/using-a-windows-form-user-control-in-mfc.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CControlBar](../../mfc/reference/ccontrolbar-class.md)  
  
 `CDialogBar`  
  
## Требования  
 **Header:**  afxext.h  
  
## См. также  
 [Пример CTRLBARS MFC](../../top/visual-cpp-samples.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CFormView Class](../../mfc/reference/cformview-class.md)   
 [CControlBar Class](../../mfc/reference/ccontrolbar-class.md)