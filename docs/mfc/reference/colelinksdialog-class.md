---
title: "COleLinksDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleLinksDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleLinksDialog class"
  - "диалоговые окна, OLE"
  - "Edit Links dialog box"
  - "OLE Edit Links dialog box"
ms.assetid: fb2eb638-2809-46db-ac74-392a732affc7
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleLinksDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый OLE диалоговое окно правка для ссылки.  
  
## Синтаксис  
  
```  
class COleLinksDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinksDialog::COleLinksDialog](../Topic/COleLinksDialog::COleLinksDialog.md)|Создает объект `COleLinksDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinksDialog::DoModal](../Topic/COleLinksDialog::DoModal.md)|Отображает диалоговое окно ссылок OLE правки.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleLinksDialog::m\_el](../Topic/COleLinksDialog::m_el.md)|Структура типа **OLEUIEDITLINKS**, который контролирует поведение диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COleLinksDialog`, когда нужно вызвать это диалоговое окно.  После того как объект `COleLinksDialog` построен, можно использовать структуру [m\_el](../Topic/COleLinksDialog::m_el.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_el` типа **OLEUIEDITLINKS**.  Дополнительные сведения об использовании этого класса см. в описании функции\-члена диалогового окна [DoModal](../Topic/COleLinksDialog::DoModal.md).  
  
> [!NOTE]
>  Мастер\-, созданный приложением код контейнера использует этот класс.  
  
 Дополнительные сведения см. в разделе макет [OLEUIEDITLINKS](http://msdn.microsoft.com/library/windows/desktop/ms678492) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окон OLE\- определенной см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleLinksDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)