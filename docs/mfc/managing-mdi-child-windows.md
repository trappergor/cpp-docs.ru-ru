---
title: Управление дочерними окнами MDI
ms.date: 11/19/2018
f1_keywords:
- MDICLIENT
helpviewer_keywords:
- MDI [MFC], child windows
- child windows [MFC], and MDICLIENT window
- MDICLIENT window [MFC]
- windows [MFC], MDI
- frame windows [MFC], MDI child windows
- child windows [MFC]
- MDI [MFC], frame windows
ms.assetid: 1828d96e-a561-48ae-a661-ba9701de6bee
ms.openlocfilehash: 6e8e3d0aa51eeea112597485a9221dcba4feda87
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84618361"
---
# <a name="managing-mdi-child-windows"></a>Управление дочерними окнами MDI

Окна главного фрейма MDI (по одному на приложение) содержат специальное дочернее окно, именуемое окном МДИКЛИЕНТ. Окно МДИКЛИЕНТ управляет клиентской областью окна главного фрейма, и само по себе имеет дочерние окна: окна документов, производные от `CMDIChildWnd` . Так как окна документов являются окнами фрейма (дочерние окна MDI), они также могут иметь собственные дочерние элементы. Во всех этих случаях родительское окно управляет его дочерними окнами и пересылает некоторые команды.

В окне фрейма MDI окно фрейма управляет окном МДИКЛИЕНТ и перемещает его в сочетании с панелями управления. Окно МДИКЛИЕНТ, в свою очередь, управляет всеми окнами дочернего фрейма MDI. На следующем рисунке показана связь между окном фрейма MDI, его окном МДИКЛИЕНТ и его дочерними окнами фрейма документа.

![Дочерние окна в окне фрейма MDI](../mfc/media/vc37gb1.gif "Дочерние окна в окне фрейма MDI") <br/>
Окна и дочерние фреймы MDI

Окно фрейма MDI также работает вместе с текущим дочерним окном MDI, если оно имеется. Окно фрейма MDI делегирует командные сообщения дочернему элементу MDI, прежде чем он попытается справиться с ними.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание окон фрейма документа](creating-document-frame-windows.md)

- [Стили окна фрейма](frame-window-styles-cpp.md)

## <a name="see-also"></a>См. также раздел

[Использование окон фрейма](using-frame-windows.md)
