---
title: Уничтожение фрейма Windows | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- PostNcDestroy
dev_langs:
- C++
helpviewer_keywords:
- Default method [MFC]
- DestroyWindow method [MFC]
- frame windows [MFC], destroying
- OnNcDestroy method, and frame windows
- document frame windows [MFC], destroying
- destroying frame windows
- MFC, frame windows
- windows [MFC], destroying
- OnClose method [MFC]
- PostNcDestroy method [MFC]
ms.assetid: 5affca77-1999-4507-a2b2-9aa226611b4b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 742ea2fedff2e4f044e46242a4152c12855ab15e
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46396159"
---
# <a name="destroying-frame-windows"></a>Уничтожение окон фрейма

Платформа MFC управляет уничтожение окна, а также создание этих окон, связанных с framework документов и представлений. Если вы создаете дополнительные окна, вы несете ответственность для уничтожение.

В структуре, когда пользователь закрывает окно фрейма окна по умолчанию [OnClose](../mfc/reference/cwnd-class.md#onclose) вызовов обработчика [DestroyWindow](../mfc/reference/cwnd-class.md#destroywindow). Последняя функция-член вызывается при уничтожении окна Windows является [OnNcDestroy](../mfc/reference/cwnd-class.md#onncdestroy), выполняющий очистку, вызывает [по умолчанию](../mfc/reference/cwnd-class.md#default) член функции для выполнения очистки Windows и наконец вызывает виртуальная функция-член [PostNcDestroy](../mfc/reference/cwnd-class.md#postncdestroy). [CFrameWnd](../mfc/reference/cframewnd-class.md) реализация `PostNcDestroy` удаляет объектом окна C++. Никогда не следует использовать C++ **удалить** оператора в окне рамки. Взамен рекомендуется использовать `DestroyWindow`.

При закрытии главного окна, закрытия приложения. Если изменяются несохраненные документы, платформа отображает окно сообщения для запроса, если документы должны сохраняться и гарантирует, что соответствующие документы сохраняются при необходимости.

## <a name="what-do-you-want-to-know-more-about"></a>Выберите для получения дополнительных сведений

- [Создание окон фрейма документа](../mfc/creating-document-frame-windows.md)

## <a name="see-also"></a>См. также

[Использование окон фрейма](../mfc/using-frame-windows.md)

