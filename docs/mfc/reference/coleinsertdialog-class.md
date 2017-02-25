---
title: "COleInsertDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleInsertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleInsertDialog class"
  - "диалоговые окна, OLE"
  - "Insert Object dialog box"
  - "OLE Insert Object dialog box"
ms.assetid: a9ec610b-abde-431e-bd01-c40159a66dbb
caps.latest.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 25
---
# COleInsertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый для вставки объекта OLE диалогового окна.  
  
## Синтаксис  
  
```  
class COleInsertDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleInsertDialog::COleInsertDialog](../Topic/COleInsertDialog::COleInsertDialog.md)|Создает объект `COleInsertDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleInsertDialog::CreateItem](../Topic/COleInsertDialog::CreateItem.md)|Создает элемент, выбранный в диалоговом окне.|  
|[COleInsertDialog::DoModal](../Topic/COleInsertDialog::DoModal.md)|Отображает диалоговое окно вставка объекта OLE.|  
|[COleInsertDialog::GetClassID](../Topic/COleInsertDialog::GetClassID.md)|Возвращает **CLSID**, связанного с выбранным элементом.|  
|[COleInsertDialog::GetDrawAspect](../Topic/COleInsertDialog::GetDrawAspect.md)|Указывает, следует ли нарисовать элемент в качестве значка.|  
|[COleInsertDialog::GetIconicMetafile](../Topic/COleInsertDialog::GetIconicMetafile.md)|Получает дескриптор к метафайлу, связанный с иконической формой этого элемента.|  
|[COleInsertDialog::GetPathName](../Topic/COleInsertDialog::GetPathName.md)|Получает полный путь к файлу, выбранному в диалоговом окне.|  
|[COleInsertDialog::GetSelectionType](../Topic/COleInsertDialog::GetSelectionType.md)|Возвращает выбранный тип объекта.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleInsertDialog::m\_io](../Topic/COleInsertDialog::m_io.md)|Структура типа **OLEUIINSERTOBJECT**, который контролирует поведение диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COleInsertDialog`, когда нужно вызвать это диалоговое окно.  После того как объект `COleInsertDialog` построен, можно использовать структуру [m\_io](../Topic/COleInsertDialog::m_io.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_io` типа **OLEUIINSERTOBJECT**.  Дополнительные сведения об использовании этого класса см. в описании функции\-члена диалогового окна [DoModal](../Topic/COleInsertDialog::DoModal.md).  
  
> [!NOTE]
>  Мастер\-, созданный приложением код контейнера использует этот класс.  
  
 Дополнительные сведения см. в разделе макет [OLEUIINSERTOBJECT](http://msdn.microsoft.com/library/windows/desktop/ms691316) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окон OLE\- определенной см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleInsertDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)