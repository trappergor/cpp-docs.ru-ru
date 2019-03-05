---
title: Классы общих диалоговых окон
ms.date: 11/04/2016
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
ms.openlocfilehash: 5efd885421d8c73c191e2a5603f37d1df85a5168
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57303077"
---
# <a name="common-dialog-classes"></a>Классы общих диалоговых окон

Помимо класса [CDialog](../mfc/reference/cdialog-class.md), MFC предоставляет несколько классов, производных от `CDialog` , инкапсулирующие часто используемым диалоговым окнам, как показано в следующей таблице. Диалоговые окна инкапсулируются называются «окон» и являются частью общей библиотекой диалоговое окно Windows (COMMDLG. БИБЛИОТЕКА DLL). Ресурсы шаблона диалогового окна и код для этих классов приведены в Windows окон, которые являются частью Windows 3.1 и более поздних версиях.

### <a name="common-dialog-classes"></a>Классы общих диалоговых окон

|Диалоговое окно производного класса|Назначение|
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
