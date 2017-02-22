---
title: "COleChangeSourceDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeSourceDialog"
  - "OLEUICHANGESOURCE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleChangeSourceDialog class"
  - "диалоговые окна, OLE"
  - "OLE Change Source dialog box"
  - "диалоговые окна OLE, Change Source"
  - "OleUIChangeSource structure"
ms.assetid: d0e08be7-21ef-45e1-97af-fe27d99e3bac
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleChangeSourceDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Общий для источника OLE диалогового окна изменения.  
  
## Синтаксис  
  
```  
class COleChangeSourceDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeSourceDialog::COleChangeSourceDialog](../Topic/COleChangeSourceDialog::COleChangeSourceDialog.md)|Создает объект `COleChangeSourceDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeSourceDialog::DoModal](../Topic/COleChangeSourceDialog::DoModal.md)|Отображает диалоговое окно " источник OLE изменения.|  
|[COleChangeSourceDialog::GetDisplayName](../Topic/COleChangeSourceDialog::GetDisplayName.md)|Получает полное отображаемое имя источника.|  
|[COleChangeSourceDialog::GetFileName](../Topic/COleChangeSourceDialog::GetFileName.md)|Получает имя файла от имени источника.|  
|[COleChangeSourceDialog::GetFromPrefix](../Topic/COleChangeSourceDialog::GetFromPrefix.md)|Возвращает префикс предыдущего источника.|  
|[COleChangeSourceDialog::GetItemName](../Topic/COleChangeSourceDialog::GetItemName.md)|Возвращает имя элемента от имени источника.|  
|[COleChangeSourceDialog::GetToPrefix](../Topic/COleChangeSourceDialog::GetToPrefix.md)|Возвращает префикс нового источника|  
|[COleChangeSourceDialog::IsValidSource](../Topic/COleChangeSourceDialog::IsValidSource.md)|Указывает, является ли источник является допустимым.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeSourceDialog::m\_cs](../Topic/COleChangeSourceDialog::m_cs.md)|Структура, которая контролирует поведение диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COleChangeSourceDialog`, когда нужно вызвать это диалоговое окно.  После того как объект `COleChangeSourceDialog` построен, можно использовать структуру [m\_cs](../Topic/COleChangeSourceDialog::m_cs.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_cs` типа [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160).  Дополнительные сведения об использовании этого класса см. в описании функции\-члена диалогового окна [DoModal](../Topic/COleChangeSourceDialog::DoModal.md).  
  
 Дополнительные сведения см. в разделе макет [OLEUICHANGESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms682160) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о специальных диалоговых окнах OLE\- см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeSourceDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)