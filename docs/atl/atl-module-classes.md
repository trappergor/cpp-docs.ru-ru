---
title: Модульные классы ATL | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
caps.latest.revision: 10
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b254edfe75cfcdaee7ab15351f7c05c3d163e301
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="atl-module-classes"></a>Модульные классы ATL
В этом разделе рассматриваются module-классы, впервые представленные в ATL 7.0.  
  
## <a name="ccommodule-replacement-classes"></a>CComModule замены классы  
 Более ранних версиях ATL используется `CComModule`. В ATL 7.0 `CComModule` функциональные возможности заменены несколько классов:  
  
-   [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) содержит сведения, необходимые для большинства приложений, использующих ATL. Содержит HINSTANCE модуля и экземпляра ресурса.  
  
-   [CAtlComModule](../atl/reference/catlcommodule-class.md) содержит сведения, необходимые для классов COM в ATL  
  
-   [CAtlWinModule](../atl/reference/catlwinmodule-class.md) содержит сведения, необходимые для классов управления окнами в ATL  
  
-   [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) включает в себя поддержку для интерфейса отладки.  
  
-   [CAtlModule](../atl/reference/catlmodule-class.md) следующие `CAtlModule`-производные классы настраиваются так, чтобы содержать данные, необходимые в типе конкретного приложения. Большинство участников в эти классы можно переопределить:  
  
    -   [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) использовать в приложениях DLL. Приводится код для стандартных экспортов.  
  
    -   [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) используется в EXE-приложения. Предоставляет код, необходимый в EXE-файла.  
  
    -   [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) обеспечивает поддержку создания Windows NT и служб Windows 2000.  
  
 `CComModule`по-прежнему доступен для обратной совместимости.  
  
## <a name="reasons-for-distributing-ccommodule-functionality"></a>Причины для распространения функциональности CComModule  
 Функциональные возможности `CComModule` был разделен на несколько новых классов по следующим причинам:  
  
-   Сделать функции в `CComModule` детальным.  
  
     Поддержка COM, управления окнами, интерфейса отладки и компонентов (DLL или EXE) приложения теперь находится в отдельных классах.  
  
-   Автоматически объявляют глобальный экземпляр каждого из этих модулей.  
  
     Глобальный экземпляр класса требуемый модуль связывается в проект.  
  
-   Удалите необходимость вызова методов Init и термин.  
  
     Методы инициализации и термин перешло в конструкторы и деструкторы классов модуля; больше не нужно вызывать Init и термин.  
  
## <a name="see-also"></a>См. также  
 [Основные понятия](../atl/active-template-library-atl-concepts.md)   
 [Общие сведения о классе](../atl/atl-class-overview.md)

