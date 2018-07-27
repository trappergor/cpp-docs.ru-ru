---
title: Последовательность деструкции окна | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- destruction, windows
- destroying windows
- sequence [MFC], window destruction
- CWnd objects [MFC], destruction sequence
- sequence [MFC]
- windows [MFC], destroying
ms.assetid: 2d819196-6240-415f-a308-db43745e616c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 3b1c67d5a6391bbfc91bbce0d06a6bb58350e9a0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33382613"
---
# <a name="window-destruction-sequence"></a>Последовательность деструкции окна
В платформе MFC, когда пользователь закрывает окно фрейма окна по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Последний функцию-член вызывается при уничтожении окна Windows [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), который не Очистка некоторых вызывает [по умолчанию](../mfc/reference/cwnd-class.md#default) член для выполнения очистки Windows и наконец вызывает виртуальная функция-член [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) реализация `PostNcDestroy` удаляет объект window C++.  
  
## <a name="what-do-you-want-to-know-more-about"></a>Выберите Дополнительные сведения  
  
-   [Выделение и освобождение памяти окна](../mfc/allocating-and-deallocating-window-memory.md)  
  
-   [Отсоединение CWnd от HWND](../mfc/detaching-a-cwnd-from-its-hwnd.md)  
  
## <a name="see-also"></a>См. также  
 [Уничтожение объектов окон](../mfc/destroying-window-objects.md)

