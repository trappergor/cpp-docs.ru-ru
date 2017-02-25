---
title: "COleConvertDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "COleConvertDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COleConvertDialog class"
  - "Преобразование - диалоговое окно"
  - "диалоговые окна, OLE"
  - "OLE Convert dialog box"
  - "диалоговые окна OLE, Convert"
ms.assetid: a7c57714-31e8-4b78-834d-8ddd1b856a1c
caps.latest.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 24
---
# COleConvertDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Дополнительные сведения см. в разделе макет [OLEUICONVERT](http://msdn.microsoft.com/library/windows/desktop/ms686657) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## Синтаксис  
  
```  
class COleConvertDialog : public COleDialog  
```  
  
## Члены  
  
### Открытые конструкторы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleConvertDialog::COleConvertDialog](../Topic/COleConvertDialog::COleConvertDialog.md)|Создает объект `COleConvertDialog`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[COleConvertDialog::DoConvert](../Topic/COleConvertDialog::DoConvert.md)|Выполняет преобразование, определенное в диалоговом окне.|  
|[COleConvertDialog::DoModal](../Topic/COleConvertDialog::DoModal.md)|Отображает диалоговое окно OLE элемента изменения.|  
|[COleConvertDialog::GetClassID](../Topic/COleConvertDialog::GetClassID.md)|Возвращает **CLSID**, связанного с выбранным элементом.|  
|[COleConvertDialog::GetDrawAspect](../Topic/COleConvertDialog::GetDrawAspect.md)|Указывает, следует ли нарисовать элемент в качестве значка.|  
|[COleConvertDialog::GetIconicMetafile](../Topic/COleConvertDialog::GetIconicMetafile.md)|Получает дескриптор к метафайлу, связанный с иконической формой этого элемента.|  
|[COleConvertDialog::GetSelectionType](../Topic/COleConvertDialog::GetSelectionType.md)|Возвращает тип выделения выбранный.|  
  
### Открытые члены данных  
  
|Имя|Описание|  
|---------|--------------|  
|[COleConvertDialog::m\_cv](../Topic/COleConvertDialog::m_cv.md)|Структура, которая контролирует поведение диалогового окна.|  
  
## Заметки  
  
> [!NOTE]
>  Мастер\-, созданный приложением код контейнера использует этот класс.  
  
 Дополнительные сведения о специальных диалоговых окнах OLE\- см. в статье [диалоговые окна в OLE](../../mfc/dialog-boxes-in-ole.md).  
  
## Иерархия наследования  
 [CObject](../Topic/CObject%20Class.md)  
  
 [CCmdTarget](../Topic/CCmdTarget%20Class.md)  
  
 [CWnd](../Topic/CWnd%20Class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../Topic/CCommonDialog%20Class.md)  
  
 [COleDialog](../../mfc/reference/coledialog-class.md)  
  
 `COleConvertDialog`  
  
## Требования  
 **Header:**  afxodlgs.h  
  
## См. также  
 [COleDialog Class](../../mfc/reference/coledialog-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [COleDialog Class](../../mfc/reference/coledialog-class.md)