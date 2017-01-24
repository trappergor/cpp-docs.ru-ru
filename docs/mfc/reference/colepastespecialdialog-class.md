---
title: "COlePasteSpecialDialog Class | Microsoft Docs"
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
  - "COlePasteSpecialDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COlePasteSpecialDialog class"
  - "диалоговые окна, Paste Special"
  - "OLE Paste Special dialog box"
  - "Paste Special dialog box"
ms.assetid: 0e82ef9a-9bbe-457e-8240-42c86a0534f7
caps.latest.revision: 24
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# COlePasteSpecialDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Общий для диалогового окна вставки объектов OLE.  
  
## Синтаксис  
  
```  
  
class COlePasteSpecialDialog : public COleDialog  
  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COlePasteSpecialDialog::COlePasteSpecialDialog](../Topic/COlePasteSpecialDialog::COlePasteSpecialDialog.md)|Создает объект `COlePasteSpecialDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COlePasteSpecialDialog::AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md)|Добавляет пользовательские форматы в список форматов, приложение может вставить.|  
|[COlePasteSpecialDialog::AddLinkEntry](../Topic/COlePasteSpecialDialog::AddLinkEntry.md)|Добавляет новую запись в список поддерживаемых форматов буфера обмена.|  
|[COlePasteSpecialDialog::AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md)|Добавляет **CF\_BITMAP**, **CF\_DIB**, `CF_METAFILEPICT` и, при необходимости, `CF_LINKSOURCE` в список форматов, приложение может вставить.|  
|[COlePasteSpecialDialog::CreateItem](../Topic/COlePasteSpecialDialog::CreateItem.md)|Создает элемент в документе контейнера с использованием указанного формата.|  
|[COlePasteSpecialDialog::DoModal](../Topic/COlePasteSpecialDialog::DoModal.md)|Отображает диалоговое окно вставка объектов OLE.|  
|[COlePasteSpecialDialog::GetDrawAspect](../Topic/COlePasteSpecialDialog::GetDrawAspect.md)|Указывает, следует ли нарисовать элемент в качестве значка или нет.|  
|[COlePasteSpecialDialog::GetIconicMetafile](../Topic/COlePasteSpecialDialog::GetIconicMetafile.md)|Получает дескриптор к метафайлу, связанный с иконической формой этого элемента.|  
|[COlePasteSpecialDialog::GetPasteIndex](../Topic/COlePasteSpecialDialog::GetPasteIndex.md)|Возвращает индекс доступных параметров вставки, выбрать пользователем.|  
|[COlePasteSpecialDialog::GetSelectionType](../Topic/COlePasteSpecialDialog::GetSelectionType.md)|Возвращает тип выделения выбранный.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COlePasteSpecialDialog::m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md)|Структура типа **OLEUIPASTESPECIAL**, который контролирует функцию диалогового окна.|  
  
## Заметки  
 Создайте объект класса `COlePasteSpecialDialog`, когда нужно вызвать это диалоговое окно.  После того как объект `COlePasteSpecialDialog` был создан, можно использовать функции\-члены [AddFormat](../Topic/COlePasteSpecialDialog::AddFormat.md) и [AddStandardFormats](../Topic/COlePasteSpecialDialog::AddStandardFormats.md) для добавления форматов буфера обмена в диалоговое окно.  Также можно использовать структуру [m\_ps](../Topic/COlePasteSpecialDialog::m_ps.md) для инициализации значений или состояния элементов управления в диалоговом окне.  Структура `m_ps` типа **OLEUIPASTESPECIAL**.  
  
 Дополнительные сведения см. в разделе макет [OLEUIPASTESPECIAL](http://msdn.microsoft.com/library/windows/desktop/ms692434) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Дополнительные сведения о диалоговых окон OLE\- определенной см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COlePasteSpecialDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [Образец OCLIENT MFC](../../top/visual-cpp-samples.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)