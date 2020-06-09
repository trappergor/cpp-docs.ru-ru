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
ms.openlocfilehash: 5f4a17bedaa50913dce1f6388dfb6b8d9ecd38da
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84617286"
---
# <a name="clipboard"></a>буфер обмена

В этом семействе статей объясняется, как реализовать поддержку буфера обмена Windows в приложениях MFC. Буфер обмена Windows используется двумя способами:

- Реализация стандартных команд меню "Правка", таких как вырезание, копирование и вставка.

- Реализация равномерной переноса данных с помощью перетаскивания OLE.

Буфер обмена — это стандартный способ передачи данных между источником и назначением Windows. Он также может быть очень полезен в операциях OLE. С появлением OLE в Windows есть два механизма обмена. Стандартный интерфейс API буфера обмена Windows по-прежнему доступен, но был дополнен механизмом преобразования данных OLE. Универсальная OLE-обмен данными (UDT) поддерживает вырезание, копирование и вставку в буфер обмена и перетаскивание.

Буфер обмена — это системная служба, общая для всего сеанса Windows, поэтому она не имеет собственного обработчика или класса. Управление буфером обмена осуществляется с помощью функций-членов класса [CWnd](reference/cwnd-class.md).

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Когда следует использовать механизм каждого буфера обмена](clipboard-when-to-use-each-clipboard-mechanism.md)

- [Использование традиционного API буфера обмена Windows](clipboard-using-the-windows-clipboard.md)

- [Использование механизма буфера обмена OLE](clipboard-using-the-ole-clipboard-mechanism.md)

- [Копирование и вставка данных](clipboard-copying-and-pasting-data.md)

- [Добавление других форматов](clipboard-adding-other-formats.md)

- [Буфер обмена Windows](/windows/win32/dataxchg/clipboard)

- [Перетаскивание OLE](drag-and-drop-ole.md)

## <a name="see-also"></a>См. также раздел

[Элементы пользовательского интерфейса](user-interface-elements-mfc.md)
