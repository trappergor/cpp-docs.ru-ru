---
title: "Классы общих диалоговых окон | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- dialog classes [MFC]
- dialog boxes [MFC], Windows common dialogs
- common dialog boxes [MFC], common dialog classes
- common dialog classes [MFC]
- MFC dialog boxes [MFC], Windows common dialogs
- Windows common dialogs [MFC]
- dialog classes [MFC], common
- common dialog boxes [MFC]
ms.assetid: 5c4f6443-896c-4b05-a7df-8169fdadc71d
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: fcbed7cec501257f03ab13447d54e081c1d46c76
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="common-dialog-classes"></a>Классы общих диалоговых окон
Помимо класса [CDialog](../mfc/reference/cdialog-class.md), MFC предоставляет несколько классов, производных от `CDialog` , инкапсулирующие часто используемые диалоговые окна, как показано в следующей таблице. Диалоговые окна, содержащийся называются «общие диалоговые окна» и являются частью общей библиотекой диалоговое окно Windows (COMMDLG. БИБЛИОТЕКА DLL). Диалоговое окно шаблона ресурсы и код для этих классов предоставляются в Windows общие диалоговые окна, являющиеся частью Windows версии 3.1 и более поздние версии.  
  
### <a name="common-dialog-classes"></a>Классы общих диалоговых окон  
  
|Диалоговое окно производного класса|Цель|  
|--------------------------|-------------|  
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Позволяет пользователю выберите цвета.|  
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Позволяет пользователю выбрать имя файла для открытия или сохранения.|  
|[Диалоговое окно CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Позволяет пользователю инициировать операцию поиска или замены в текстовом файле.|  
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Позволяет пользователю задать шрифт.|  
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Позволяет пользователю указать сведения для задания печати.|  
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Лист свойств печати Windows 2000.|  
  
 Дополнительные сведения о классы общих диалоговых окон, в разделе имена отдельных классов в *Справочник по библиотеке MFC*. MFC также предоставляет ряд классов стандартное диалоговое окно используется для OLE. Сведения об этих классах см. в разделе базового класса, [COleDialog](../mfc/reference/coledialog-class.md)в *Справочник по библиотеке MFC*.  
  
 Три других классов MFC имеют характеристики как диалоговое окно. Дополнительные сведения о классах [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), просмотреть классы *Справочник по библиотеке MFC*. Дополнительные сведения о классе [CDialogBar](../mfc/reference/cdialogbar-class.md), в разделе [диалоговые панели](../mfc/dialog-bars.md).  
  
## <a name="see-also"></a>См. также  
 [Диалоговые окна](../mfc/dialog-boxes.md)   
 [Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)   
 [Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)

