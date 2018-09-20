---
title: Классы общих диалоговых окон | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 0a937ded9fe356627e36ad0262e749446553aa91
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46379727"
---
# <a name="common-dialog-classes"></a>Классы общих диалоговых окон

Помимо класса [CDialog](../mfc/reference/cdialog-class.md), MFC предоставляет несколько классов, производных от `CDialog` , инкапсулирующие часто используемым диалоговым окнам, как показано в следующей таблице. Диалоговые окна инкапсулируются называются «окон» и являются частью общей библиотекой диалоговое окно Windows (COMMDLG. БИБЛИОТЕКА DLL). Ресурсы шаблона диалогового окна и код для этих классов приведены в Windows окон, которые являются частью Windows 3.1 и более поздних версиях.

### <a name="common-dialog-classes"></a>Классы общих диалоговых окон

|Диалоговое окно производного класса|Цель|
|--------------------------|-------------|
|[CColorDialog](../mfc/reference/ccolordialog-class.md)|Позволяет пользователю выберите цвета.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Позволяет пользователю выбрать имя файла для открытия или сохранения.|
|[Диалоговое окно CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Позволяет пользователю инициировать поиска и замены в текстовом файле.|
|[CFontDialog](../mfc/reference/cfontdialog-class.md)|Позволяет пользователю указать шрифт.|
|[CPrintDialog](../mfc/reference/cprintdialog-class.md)|Позволяет пользователю указать сведения для задания печати.|
|[CPrintDialogEx](../mfc/reference/cprintdialogex-class.md)|Страница свойств печати Windows.|

Дополнительные сведения о классы общих диалоговых окон, см. в разделе имена отдельных классов в *Справочник по библиотеке MFC*. MFC также предоставляет ряд классов стандартное диалоговое окно используется для OLE. Сведения об этих классах см. в разделе базового класса, [COleDialog](../mfc/reference/coledialog-class.md)в *Справочник по библиотеке MFC*.

Три других классов в MFC имеют диалоговое окно подобные характеристики. Сведения о классах [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md), и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md), см. в разделе классы *Справочник по библиотеке MFC*. Сведения о классе [CDialogBar](../mfc/reference/cdialogbar-class.md), см. в разделе [диалоговые панели](../mfc/dialog-bars.md).

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Жизненный цикл диалогового окна](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)

