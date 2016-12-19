---
title: "COleChangeIconDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleChangeIconDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Change Icon dialog box"
  - "COleChangeIconDialog class"
  - "диалоговые окна, OLE"
  - "OLE Change Icon dialog box"
  - "диалоговые окна OLE, Change Icon"
ms.assetid: 8d6e131b-ddbb-4dff-a432-f239efda8e3d
caps.latest.revision: 22
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COleChangeIconDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Используемый OLE диалогового окна для значка изменения.  
  
## Синтаксис  
  
```  
class COleChangeIconDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeIconDialog::COleChangeIconDialog](../Topic/COleChangeIconDialog::COleChangeIconDialog.md)|Создает объект `COleChangeIconDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeIconDialog::DoChangeIcon](../Topic/COleChangeIconDialog::DoChangeIcon.md)|Выполняет изменение, указанное в диалоговом окне.|  
|[COleChangeIconDialog::DoModal](../Topic/COleChangeIconDialog::DoModal.md)|Отображает диалоговое окно значок изменения OLE 2.|  
|[COleChangeIconDialog::GetIconicMetafile](../Topic/COleChangeIconDialog::GetIconicMetafile.md)|Получает дескриптор к метафайлу, связанный с иконической формой этого элемента.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleChangeIconDialog::m\_ci](../Topic/COleChangeIconDialog::m_ci.md)|Структура, которая контролирует поведение диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COleChangeIconDialog`, когда нужно вызвать это диалоговое окно.  После того как объект `COleChangeIconDialog` построен, можно использовать структуру [m\_ci](../Topic/COleChangeIconDialog::m_ci.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_ci` типа **OLEUICHANGEICON**.  Дополнительные сведения об использовании этого класса см. в описании функции\-члена диалогового окна [DoModal](../Topic/COleChangeIconDialog::DoModal.md).  
  
 Дополнительные сведения см. в разделе макет [OLEUICHANGEICON](http://msdn.microsoft.com/library/windows/desktop/ms680098) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о специальных диалоговых окнах OLE\- см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleChangeIconDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)