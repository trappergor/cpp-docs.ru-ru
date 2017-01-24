---
title: "Классы общих диалоговых окон | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "общие диалоговые окна [C++]"
  - "общие диалоговые окна [C++], классы общих диалоговых окон"
  - "классы общих диалоговых окон [C++]"
  - "диалоговые окна [C++], общие диалоговые окна Windows"
  - "классы диалоговых окон [C++]"
  - "классы диалоговых окон [C++], общий"
  - "диалоговые окна MFC, общие диалоговые окна Windows"
  - "общие диалоговые окна Windows [C++]"
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Классы общих диалоговых окон
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

В дополнение к классу [CDialog](../mfc/reference/cdialog-class.md), MFC предоставляет несколько классов, производных от `CDialog`, которые инкапсулируют часто используемые диалоговые окна, как показано в следующей таблице.  Инкапсулированные диалоговые окна называются «стандартные диалоговые окна» и в библиотеку стандартного диалогового окна печати Windows \(COMMDLG.DLL\).  Ресурсы и код шаблона диалоговых окон для этих классов предоставляемых в стандартных диалоговых окнах Windows, которые являются частью версий Windows 3.1 и более поздних версиях.  
  
### Классы стандартного диалогового окна  
  
|Производный класс диалогового окна|Назначение|  
|----------------------------------------|----------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Позволяет цветам пользователя отборным.|  
|[CFileDialog](../Topic/CFileDialog%20Class.md)|Позволяет пользователю выбрать имя файла для открытия или сохранения.|  
|[CFindReplaceDialog](../Topic/CFindReplaceDialog%20Class.md)|Позволяет пользователю начать находку или заменить операцию в текстовом файле.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Позволяет пользователю указать шрифт.|  
|[CPrintDialog](../Topic/CPrintDialog%20Class.md)|Позволяет пользователю сведений для задания печати.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Страница свойств печати в Windows 2000.|  
  
 Дополнительные сведения о классы стандартного диалогового окна, просмотреть отдельные имена классов в справочнике по *MFC*.  MFC также предоставляет несколько стандартных классов диалоговых окон, используемых для OLE.  Дополнительные сведения об этих классах см. в разделе [COleDialog](../mfc/reference/coledialog-class.md), базовый класс в *справочнике по MFC*.  
  
 3 Другого класса в MFC имеют похожие характеристики на диалог.  Дополнительные сведения о классах [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md) и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md) классов см. в *справочнике по MFC*.  Дополнительные сведения о классе [CDialogBar](../mfc/reference/cdialogbar-class.md) см. в разделе [Диалоговые панели](../mfc/dialog-bars.md).  
  
## См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)