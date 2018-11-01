---
title: Потоковые операции с использованием элементов управления "Rich Edit"
ms.date: 11/04/2016
helpviewer_keywords:
- CRichEditCtrl class [MFC], stream operations
- CRichEditCtrl class [MFC], stream storage
- rich edit controls [MFC], stream operations
- storage, stream in CRichEditCtrl
- stream operations in CRichEditCtrl
- stream storage and CRichEditCtrl
ms.assetid: 110b4684-1e76-4ca6-9ef0-5bc8b2d93c78
ms.openlocfilehash: 099b29a3a3ff1337c71d14d1ae7bfa0a182a6903
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50584415"
---
# <a name="stream-operations-in-rich-edit-controls"></a>Потоковые операции с использованием элементов управления "Rich Edit"

Потоки можно использовать для передачи данных в или из нее в элементе управления rich edit ([CRichEditCtrl](../mfc/reference/cricheditctrl-class.md)). Поток определяется [EDITSTREAM](/windows/desktop/api/richedit/ns-richedit-_editstream) структуру, которая задает буфер и функцию обратного вызова, определяемые приложением.

Для чтения данных в форматированного текста элемента управления edit (т. е. поток данных в), используйте [StreamIn](../mfc/reference/cricheditctrl-class.md#streamin) функция-член. Элемент управления многократно вызывает функцию обратного вызова, определяемые приложением, которая передает часть данных в буфер каждый раз.

Чтобы сохранить содержимое форматированного текста ввода элемента управления (то есть потоковую передачу данных out), можно использовать [StreamOut](../mfc/reference/cricheditctrl-class.md#streamout) функция-член. Элемент управления постоянно записывает в буфер, а затем вызывает функцию обратного вызова, определяемые приложением. Для каждого вызова функции обратного вызова сохраняет содержимое буфера.

## <a name="see-also"></a>См. также

[Использование CRichEditCtrl](../mfc/using-cricheditctrl.md)<br/>
[Элементы управления](../mfc/controls-mfc.md)

