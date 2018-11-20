---
title: Отношение между объектом окна C++ и HWND
ms.date: 11/19/2018
f1_keywords:
- HWND
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
ms.openlocfilehash: fcd885fbaf7e81d68bcd51edc4b74c553f70578b
ms.sourcegitcommit: 9e891eb17b73d98f9086d9d4bfe9ca50415d9a37
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 11/20/2018
ms.locfileid: "52176865"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Отношение между объектом окна C++ и HWND

Окно *объект* — это объект C++ `CWnd` класс (или производного класса), программа создает напрямую. Он поставляется и переходит в ответ на вызовы программы конструктор и деструктор. Windows *окно*, с другой стороны, – это прозрачный дескриптор на внутреннюю структуру данных Windows, соответствующий окна и потребляет системные ресурсы, если он присутствует. Окно Windows идентифицируется «дескриптор окна» (`HWND`) и создается после `CWnd` создается путем вызова `Create` функция-член класса `CWnd`. Действием пользователя или вызовом программы может уничтожить окно. Дескриптор окна хранится в объекте окно *m_hWnd* переменной-члена. На рисунке показана связь между объектом окна C++ и окно Windows. Создание окон рассматривается в [Создание Windows](../mfc/creating-windows.md). Уничтожение окон рассматривается в [уничтожение объектов окон](../mfc/destroying-window-objects.md).

![CWnd объект окна и в появившемся окне](../mfc/media/vc37fj1.gif "CWnd объект окна и в появившемся окне") <br/>
Объект окна и окна Windows

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)
