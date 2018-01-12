---
title: "В окне (классов ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- CWindow class, about CWindow class
- windows [C++], ATL
ms.assetid: b3b9cc8e-4287-486b-b080-38852bc2943a
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a2be573e10190b385274de9afab498c77a094550
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="using-a-window"></a>С помощью окна
Класс [CWindow](../atl/reference/cwindow-class.md) дает возможность использовать окно. После присоединения в окне `CWindow` объекта, затем можно вызвать `CWindow` методы для управления окном. `CWindow`также содержит `HWND` оператор преобразования `CWindow` объект `HWND`. Таким образом можно передать `CWindow` объект любая функция, которая требует дескриптора окна. Вы можете легко сочетать `CWindow` вызовы методов и вызовы функций Win32, без создания временных объектов.  
  
 Поскольку `CWindow` имеет член данных только два (дескриптор окна и размеры по умолчанию), не накладывает дополнительные затраты на ваш код. Кроме того, многие из `CWindow` методы просто используйте соответствующие функции Win32 API. С помощью `CWindow`, `HWND` член автоматически передается в функцию Win32.  
  
 Помимо использования `CWindow` напрямую, также являются производными от него, чтобы добавить данные или код в класс. ATL, сам является производным три класса из `CWindow`: [CWindowImpl](../atl/implementing-a-window.md), [CDialogImpl](../atl/implementing-a-dialog-box.md), и [CContainedWindowT](../atl/using-contained-windows.md).  
  
## <a name="see-also"></a>См. также  
 [Классы окон](../atl/atl-window-classes.md)

