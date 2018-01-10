---
title: "Windows поддерживает классов (ATL) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.windows
dev_langs: C++
helpviewer_keywords:
- ATL, windows
- windows [C++], ATL
ms.assetid: 750b14d5-d787-4d2b-9728-ac199ccad489
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 308f9deada47998c2f639d01ea5b9fdc9d04faa5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
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

