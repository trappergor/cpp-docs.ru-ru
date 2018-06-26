---
title: Связь между объектом окна C++ и HWND | Документы Microsoft
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
ms.openlocfilehash: 3864de8b3133fd2284b3ce57b75b30d8f41c26a7
ms.sourcegitcommit: 060f381fe0807107ec26c18b46d3fcb859d8d2e7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/25/2018
ms.locfileid: "36928532"
---
# <a name="relationship-between-a-c-window-object-and-an-hwnd"></a>Отношение между объектом окна C++ и HWND
Окно *объекта* — это объект C++ `CWnd` класс (или производный класс), программа создает напрямую. Он поставляется и переходит в ответ на вызовы конструктора и деструктора программы. Windows *окна*, с другой стороны, является непрозрачный дескриптор для внутренней структуры данных Windows, соответствующего окна и потребляет системные ресурсы, если они есть. Окно Windows идентифицируется «дескриптор окна» (`HWND`) и создается после `CWnd` создается путем вызова `Create` функции-члена класса `CWnd`. Окно может уничтожить вызов программы либо на действия пользователя. Дескриптор окна, хранящихся в объекте окна *m_hWnd* переменной-члена. На следующем рисунке показана связь между объектом окна C++ и окно Windows. Создание окон рассматривается в [Создание Windows](../mfc/creating-windows.md). Уничтожение окон рассматривается в [уничтожение объектов окон](../mfc/destroying-window-objects.md).  
  
 ![CWnd объект окна и в появившемся окне](../mfc/media/vc37fj1.gif "vc37fj1")  
Объект окна и окна Windows  
  
## <a name="see-also"></a>См. также  
 [Объекты окон](../mfc/window-objects.md)

