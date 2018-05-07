---
title: Windows поддерживает классов (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- vc.atl.windows
dev_langs:
- C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: c2095e5141dfdd320bae0e7aa69ffd4b3c9fe9a9
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="windows-support-classes"></a>Классы поддержки Windows
Следующие классы обеспечивают поддержку windows.  
  
-   [_U_MENUorID](../atl/reference/u-menuorid-class.md) предоставляет оболочки для **CreateWindow** и **CreateWindowEx**.  
  
-   [CWindow](../atl/reference/cwindow-class.md) содержит методы для управления окном. `CWindow` — это базовый класс для `CWindowImpl`, `CDialogImpl` и `CContainedWindow`.  
  
-   [CWindowImpl](../atl/reference/cwindowimpl-class.md) реализует окно, в зависимости от нового класса окна. Также позволяет подкласс или суперкласса окна.  
  
-   [CDialogImpl](../atl/reference/cdialogimpl-class.md) реализует диалоговое окно.  
  
-   [CAxDialogImpl](../atl/reference/caxdialogimpl-class.md) реализует диалоговое окно (модальные и немодальные), на котором размещена элементы управления ActiveX.  
  
-   [CSimpleDialog](../atl/reference/csimpledialog-class.md) реализует диалоговое окно (модальные и немодальные) с базовыми функциями.  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) манипулирует окна, на котором размещается элемент управления ActiveX.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) содержит методы для работы окно, которое размещает элемент ActiveX, а также поддержка размещения Лицензированные элементы управления ActiveX.  
  
-   [CContainedWindowT](../atl/reference/ccontainedwindowt-class.md) реализует окно, содержатся внутри другого объекта.  
  
-   [CWndClassInfo](../atl/reference/cwndclassinfo-class.md) управляет данными нового класса окна.  
  
-   [CDynamicChain](../atl/reference/cdynamicchain-class.md) поддержка динамического объединения схемы сообщений.  
  
-   [CMessageMap](../atl/reference/cmessagemap-class.md) позволяет объекту предоставлять свои сообщения сопоставляется с другими объектами.  
  
-   [CWinTraits](../atl/reference/cwintraits-class.md) предоставляет простой способ стандартизации признаки объект ATL окна.  
  
-   [CWinTraitsOR](../atl/reference/cwintraitsor-class.md) предоставляет значения по умолчанию для стилей окна и расширенные стили, используемые для создания окна. Эти значения добавляются с помощью оператора логического или, для значений, предоставленных во время создания окна.  
  
## <a name="related-articles"></a>Связанные статьи  
 [Классы окон ATL](../atl/atl-window-classes.md)  
  
 [Учебник по ATL](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)   
 [Макросы схемы сообщений](../atl/reference/message-map-macros-atl.md)   
 [Макросы класса окна](../atl/reference/window-class-macros.md)

