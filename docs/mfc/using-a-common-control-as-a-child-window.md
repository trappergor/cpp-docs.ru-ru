---
title: Использование общего элемента управления как дочернего окна
ms.date: 11/04/2016
helpviewer_keywords:
- controls [MFC], using as child windows
- windows [MFC], common controls as
- child windows [MFC], common controls as
- common controls [MFC], child windows
- Windows common controls [MFC], child windows
ms.assetid: 608f7d47-7854-4fce-bde9-856c51e76753
ms.openlocfilehash: 827690f273852dee8f9461aa9af51f1cf7f4ce6e
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62180574"
---
# <a name="using-a-common-control-as-a-child-window"></a>Использование общего элемента управления как дочернего окна

Любой из стандартных элементов управления Windows может использоваться как любое другое окно дочернего окна. Следующая процедура описывается динамическое создание общего элемента управления и затем работать с ними.

### <a name="to-use-a-common-control-as-a-child-window"></a>Использование общего элемента управления как дочернего окна

1. Определите элемент управления в связанный класс или обработчика.

1. Использование элемента управления переопределением [CWnd::Create](../mfc/reference/cwnd-class.md#create) метод для создания элемента управления Windows.

1. После создания элемента управления (уже в `OnCreate` обработчик Если подкласса элемента управления), можно управлять элемента управления, используя свои функции-члены. См. в описаниях отдельных элементов управления в [элементов управления](../mfc/controls-mfc.md) Дополнительные сведения о методах.

1. По окончании работы с элементом управления использовать [CWnd::DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow) уничтожение элемента управления.

## <a name="see-also"></a>См. также

[Создание и использование элементов управления](../mfc/making-and-using-controls.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)
