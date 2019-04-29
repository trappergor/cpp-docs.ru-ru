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
ms.openlocfilehash: 8cf8856be7166768c507932184e257cf69b0eb35
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62309333"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Отношение между объектом окна C++ и HWND

Окно *объект* — это объект C++ `CWnd` класс (или производного класса), программа создает напрямую. Он поставляется и переходит в ответ на вызовы программы конструктор и деструктор. Windows *окно*, с другой стороны, – это прозрачный дескриптор на внутреннюю структуру данных Windows, соответствующий окна и потребляет системные ресурсы, если он присутствует. Окно Windows идентифицируется «дескриптор окна» (`HWND`) и создается после `CWnd` создается путем вызова `Create` функция-член класса `CWnd`. Действием пользователя или вызовом программы может уничтожить окно. Дескриптор окна хранится в объекте окно *m_hWnd* переменной-члена. На рисунке показана связь между объектом окна C++ и окно Windows. Создание окон рассматривается в [Создание Windows](../mfc/creating-windows.md). Уничтожение окон рассматривается в [уничтожение объектов окон](../mfc/destroying-window-objects.md).

![CWnd объект окна и в появившемся окне](../mfc/media/vc37fj1.gif "CWnd объект окна и в появившемся окне") <br/>
Объект окна и окна Windows

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)
