---
title: Связь между объектом окна C++ и HWND | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: conceptual
f1_keywords:
- HWND
dev_langs:
- C++
helpviewer_keywords:
- Windows window [MFC]
- window objects [MFC], HWND and
- HWND [MFC]
- CWnd class [MFC], HWND
- HWND, window objects [MFC]
ms.assetid: f2e76340-6691-4ee6-9424-0345634a9469
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 844f62b110f54ba3e2c8909a78d58c9f2c01dcac
ms.sourcegitcommit: 799f9b976623a375203ad8b2ad5147bd6a2212f0
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/19/2018
ms.locfileid: "46392818"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Отношение между объектом окна C++ и HWND

Окно *объект* — это объект C++ `CWnd` класс (или производного класса), программа создает напрямую. Он поставляется и переходит в ответ на вызовы программы конструктор и деструктор. Windows *окно*, с другой стороны, – это прозрачный дескриптор на внутреннюю структуру данных Windows, соответствующий окна и потребляет системные ресурсы, если он присутствует. Окно Windows идентифицируется «дескриптор окна» (`HWND`) и создается после `CWnd` создается путем вызова `Create` функция-член класса `CWnd`. Действием пользователя или вызовом программы может уничтожить окно. Дескриптор окна хранится в объекте окно *m_hWnd* переменной-члена. На рисунке показана связь между объектом окна C++ и окно Windows. Создание окон рассматривается в [Создание Windows](../mfc/creating-windows.md). Уничтожение окон рассматривается в [уничтожение объектов окон](../mfc/destroying-window-objects.md).

![CWnd объект окна и в появившемся окне](../mfc/media/vc37fj1.gif "vc37fj1") объект окна и окна Windows

## <a name="see-also"></a>См. также

[Объекты окон](../mfc/window-objects.md)

