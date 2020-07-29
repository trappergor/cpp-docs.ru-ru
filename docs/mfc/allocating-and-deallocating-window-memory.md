---
title: Выделение и освобождение памяти окна
ms.date: 11/04/2016
helpviewer_keywords:
- memory allocation, window objects
- memory deallocation
- storage for window objects [MFC]
- memory deallocation, window memory
- window objects [MFC], deallocating memory for
- storage for window objects [MFC], allocating
ms.assetid: 7c962539-8461-4846-b5ca-fe3b15c313dc
ms.openlocfilehash: 33d471b41c8f1fd670e25626049ecd9b06b034e1
ms.sourcegitcommit: 1f009ab0f2cc4a177f2d1353d5a38f164612bdb1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/27/2020
ms.locfileid: "87195204"
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна

Не используйте **`delete`** оператор C++ для уничтожения окна или представления фрейма. Вместо этого вызовите `CWnd` функцию члена `DestroyWindow` . Таким образом, окна фрейма должны выделяться в куче с оператором **`new`** . Будьте внимательны при выделении окон фрейма в кадре стека или глобально. Другие окна должны выделяться в кадре стека везде, где это возможно.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание окон](creating-windows.md)

- [Последовательность уничтожения окна](window-destruction-sequence.md)

- [Отсоединение CWnd от HWND](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>См. также раздел

[Уничтожение объектов Window](destroying-window-objects.md)
