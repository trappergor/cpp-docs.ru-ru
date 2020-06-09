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
ms.openlocfilehash: 2efe095a6d5b71321cbbe56fdee662509baa4573
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84619027"
---
# <a name="common-dialog-classes"></a>Классы общих диалоговых окон

В дополнение к классу [CDialog](reference/cdialog-class.md)MFC предоставляет несколько классов, производных от `CDialog` широко используемых диалоговых окон, как показано в следующей таблице. Инкапсулированные диалоговые окна называются общими диалоговыми окнами и являются частью библиотеки общих диалоговых окон Windows (КОММДЛГ. DLL). Ресурсы шаблонов диалогового окна и код для этих классов приведены в общих диалоговых окнах Windows, которые являются частью Windows версии 3,1 и более поздних.

### <a name="common-dialog-classes"></a>Классы общих диалоговых окон

|Производный класс диалогового окна|Назначение|
|--------------------------|-------------|
|[CColorDialog](reference/ccolordialog-class.md)|Позволяет пользователю выбирать цвета.|
|[CFileDialog](reference/cfiledialog-class.md)|Позволяет пользователю выбрать имя файла для открытия или сохранения.|
|[CFindReplaceDialog](reference/cfindreplacedialog-class.md)|Позволяет пользователю инициировать операцию поиска или замены в текстовом файле.|
|[CFontDialog](reference/cfontdialog-class.md)|Позволяет пользователю указать шрифт.|
|[CPrintDialog](reference/cprintdialog-class.md)|Позволяет пользователю указать сведения для задания печати.|
|[CPrintDialogEx](reference/cprintdialogex-class.md)|Страница свойств печати Windows.|

Дополнительные сведения о классах общих диалоговых окон см. в разделе имена отдельных классов в *справочнике по MFC*. MFC также предоставляет ряд стандартных классов диалоговых окон, используемых для OLE. Дополнительные сведения об этих классах см. в разделе базовый класс [коледиалог](reference/coledialog-class.md)в *справочнике по MFC*.

Три других класса в MFC имеют характеристики, схожие с диалогом. Сведения о классах [CFormView](reference/cformview-class.md), [CRecordView](reference/crecordview-class.md)и [CDaoRecordView](reference/cdaorecordview-class.md)см. в разделе классы в *справочнике по MFC*. Дополнительные сведения о классе [CDialogBar](reference/cdialogbar-class.md)см. в разделе [панели диалоговых окон](dialog-bars.md).

## <a name="see-also"></a>См. также раздел

[Диалоговые окна](dialog-boxes.md)<br/>
[Работа с диалоговыми окнами в MFC](life-cycle-of-a-dialog-box.md)<br/>
[Диалоговые окна в OLE](dialog-boxes-in-ole.md)
