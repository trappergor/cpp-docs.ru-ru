---
title: Уничтожение окон фрейма
ms.date: 11/04/2016
f1_keywords:
- PostNcDestroy
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
ms.openlocfilehash: 20eefa2be6d0e0df4585834bae5c37cd258610a7
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87214143"
---
# <a name="destroying-frame-windows"></a>Уничтожение окон фрейма

Платформа MFC управляет уничтожением окна, а также созданием окон, связанных с документами и представлениями платформы. Если вы создаете дополнительные окна, вы несете ответственность за их уничтожение.

В платформе, когда пользователь закрывает окно фрейма, обработчик [OnClose](reference/cwnd-class.md#onclose) окна по умолчанию вызывает [дестройвиндов](reference/cwnd-class.md#destroywindow). Последняя функция-член, вызываемая при уничтожении окна Windows, — это [OnNcDestroy](reference/cwnd-class.md#onncdestroy), который выполняет некоторую очистку, вызывает функцию-член [по умолчанию](reference/cwnd-class.md#default) для выполнения очистки Windows и, наконец, вызывает виртуальную функцию-член [постнкдестрой](reference/cwnd-class.md#postncdestroy). Реализация [CFrameWnd](reference/cframewnd-class.md) `PostNcDestroy` удаляет объект окна C++. Никогда не следует использовать оператор C++ **`delete`** в окне фрейма. Используйте вместо этого `DestroyWindow`.

При закрытии главного окна приложение закрывается. При наличии измененных несохраненных документов платформа отображает окно сообщения, в котором следует указать, следует ли сохранять документы, и обеспечить сохранение соответствующих документов при необходимости.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание окон фрейма документа](creating-document-frame-windows.md)

## <a name="see-also"></a>См. также раздел

[Использование окон фрейма](using-frame-windows.md)
