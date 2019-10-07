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
ms.openlocfilehash: d11d0978763d9599b0471a8e994f15a267f7cb8f
ms.sourcegitcommit: 1e6386be9084f70def7b3b8b4bab319a117102b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/30/2019
ms.locfileid: "71685558"
---
# <a name="common-dialog-classes"></a>Классы общих диалоговых окон

В дополнение к классу [CDialog](../mfc/reference/cdialog-class.md)MFC предоставляет несколько классов, производных от `CDialog`, которые инкапсулируют часто используемые диалоговые окна, как показано в следующей таблице. Инкапсулированные диалоговые окна называются общими диалоговыми окнами и являются частью библиотеки общих диалоговых окон Windows (КОММДЛГ. DLL). Ресурсы шаблонов диалогового окна и код для этих классов приведены в общих диалоговых окнах Windows, которые являются частью Windows версии 3,1 и более поздних.

### <a name="common-dialog-classes"></a>Классы общих диалоговых окон

|Производный класс диалогового окна|Цель|
|--------------------------|-------------|
|[кколордиалог](../mfc/reference/ccolordialog-class.md)|Позволяет пользователю выбирать цвета.|
|[CFileDialog](../mfc/reference/cfiledialog-class.md)|Позволяет пользователю выбрать имя файла для открытия или сохранения.|
|[Диалоговое CFindReplaceDialog](../mfc/reference/cfindreplacedialog-class.md)|Позволяет пользователю инициировать операцию поиска или замены в текстовом файле.|
|[кфонтдиалог](../mfc/reference/cfontdialog-class.md)|Позволяет пользователю указать шрифт.|
|[кпринтдиалог](../mfc/reference/cprintdialog-class.md)|Позволяет пользователю указать сведения для задания печати.|
|[кпринтдиаложекс](../mfc/reference/cprintdialogex-class.md)|Страница свойств печати Windows.|

Дополнительные сведения о классах общих диалоговых окон см. в разделе имена отдельных классов в *справочнике по MFC*. MFC также предоставляет ряд стандартных классов диалоговых окон, используемых для OLE. Дополнительные сведения об этих классах см. в разделе базовый класс [коледиалог](../mfc/reference/coledialog-class.md)в *справочнике по MFC*.

Три других класса в MFC имеют характеристики, схожие с диалогом. Сведения о классах [CFormView](../mfc/reference/cformview-class.md), [CRecordView](../mfc/reference/crecordview-class.md)и [CDaoRecordView](../mfc/reference/cdaorecordview-class.md)см. в разделе классы в *справочнике по MFC*. Дополнительные сведения о классе [CDialogBar](../mfc/reference/cdialogbar-class.md)см. в разделе [панели диалоговых окон](../mfc/dialog-bars.md).

## <a name="see-also"></a>См. также

[Диалоговые окна](../mfc/dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](../mfc/life-cycle-of-a-dialog-box.md)<br/>
[Диалоговые окна в OLE](../mfc/dialog-boxes-in-ole.md)
