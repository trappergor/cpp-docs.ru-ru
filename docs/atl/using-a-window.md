---
title: В окне (классов ATL) | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 44b9988c0ecde4d0aee917fea686ec6511473318
ms.sourcegitcommit: 26fff80635bd1d51bc51899203fddfea8b29b530
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/05/2018
ms.locfileid: "37847928"
---
# <a name="using-a-window"></a>В окне
Класс [CWindow](../atl/reference/cwindow-class.md) позволяет использовать окно. После присоединения окно `CWindow` объекта, затем можно вызвать `CWindow` методы для управления окном. `CWindow` также содержит оператор HWND для преобразования `CWindow` объект HWND. Таким образом вы можете передать `CWindow` объект для любой функции, требующей дескриптор окна. Можно легко смешивать `CWindow` вызовов методов и вызовы функций Win32, без создания временных объектов.  
  
 Так как `CWindow` имеет только два данные-член (дескриптор окна и размеры по умолчанию), он не создать нагрузку на ваш код. Кроме того, многие из `CWindow` методы просто переносить соответствующие функции Win32 API. С помощью `CWindow`, элемент HWND автоматически передается в функцию Win32.  
  
 Помимо использования `CWindow` напрямую, также являются производными от его, чтобы добавить данные или код в класс. ATL, сам является производным три класса из `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), и [CContainedWindowT](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

