---
title: буфер обмена
ms.date: 11/04/2016
helpviewer_keywords:
- cutting and copying data
- copying data
- Clipboard
- Clipboard, programming
- transferring data
ms.assetid: a71b2824-1f14-4914-8816-54578d73ad4e
ms.openlocfilehash: 4fcf53f1d861a85d830d0fb4244e8af9c11af163
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57293294"
---
# <a name="clipboard"></a>буфер обмена

Этот сборник статей описываются способы реализации поддержки в буфер обмена Windows в приложениях MFC. В буфер обмена Windows используется двумя способами:

- Реализация стандартных команд в меню, таких как операции вырезания, копирования и вставки.

- Реализация универсальный данных передачи с помощью перетаскивания и drop (OLE).

Буфер обмена — это стандартный метод Windows передачи данных между источником и назначением. Также может быть полезным при операции OLE. С появлением OLE существует два механизма буфера обмена в Windows. Стандартный API буфера обмена Windows по-прежнему доступна, но она была дополнена механизм передачи данных OLE. Передача OLE универсальный данных (UDT) поддерживает операции вырезания, копирования и вставки с буфером обмена и перетащите.

Буфер обмена — это системная служба, совместно используется весь сеанс Windows, поэтому он не имеет дескриптор или свой собственный класс. Вы управляете буфере посредством функции-члены класса [CWnd](../mfc/reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Использование механизма буфера обмена](../mfc/clipboard-when-to-use-each-clipboard-mechanism.md)

- [С помощью традиционных API буфера обмена Windows](../mfc/clipboard-using-the-windows-clipboard.md)

- [Использование механизма буфера обмена OLE](../mfc/clipboard-using-the-ole-clipboard-mechanism.md)

- [Копирование и вставка данных](../mfc/clipboard-copying-and-pasting-data.md)

- [Добавление других форматов](../mfc/clipboard-adding-other-formats.md)

- [В буфер обмена Windows](https://msdn.microsoft.com/library/ms648709)

- [Реализация перетаскивание (OLE)](../mfc/drag-and-drop-ole.md)

## <a name="see-also"></a>См. также

[Элементы пользовательского интерфейса](../mfc/user-interface-elements-mfc.md)
