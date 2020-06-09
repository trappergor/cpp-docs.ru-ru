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
ms.openlocfilehash: 02546559183d0e14973bc2e5ccb26a4570a39b1e
ms.sourcegitcommit: c21b05042debc97d14875e019ee9d698691ffc0b
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/09/2020
ms.locfileid: "84623268"
---
# <a name="allocating-and-deallocating-window-memory"></a>Выделение и освобождение памяти окна

Не используйте оператор **Delete** C++ для уничтожения окна или представления фрейма. Вместо этого вызовите `CWnd` функцию члена `DestroyWindow` . Таким образом, окна фрейма должны выделяться в куче с помощью оператора **New**. Будьте внимательны при выделении окон фрейма в кадре стека или глобально. Другие окна должны выделяться в кадре стека везде, где это возможно.

## <a name="what-do-you-want-to-know-more-about"></a>Что вы хотите узнать подробнее

- [Создание окон](creating-windows.md)

- [Последовательность уничтожения окна](window-destruction-sequence.md)

- [Отсоединение CWnd от HWND](detaching-a-cwnd-from-its-hwnd.md)

## <a name="see-also"></a>См. также раздел

[Уничтожение объектов Window](destroying-window-objects.md)
