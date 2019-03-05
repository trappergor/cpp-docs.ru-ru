---
title: Модульные классы ATL
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2fe659b47893f821aab4cda31ab1a4e9a6788ec6
ms.sourcegitcommit: c3093251193944840e3d0a068ecc30e6449624ba
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/04/2019
ms.locfileid: "57295465"
---
# <a name="atl-module-classes"></a>Модульные классы ATL

В этом разделе рассматриваются классы модулей, впервые представленные в ATL 7.0.

## <a name="ccommodule-replacement-classes"></a>Классы замены CComModule

Более ранних версиях ATL используется `CComModule`. В ATL 7.0 `CComModule` функциональные возможности заменены несколько классов:

- [CAtlBaseModule](../atl/reference/catlbasemodule-class.md) содержит сведения, необходимые для большинства приложений, использующих ATL. Содержит объект HINSTANCE модуля и экземпляра ресурса.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) содержит сведения, необходимые для классов COM в ATL

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) содержит сведения, необходимые для классов управления окнами в ATL

- [CAtlDebugInterfacesModule](../atl/reference/catldebuginterfacesmodule-class.md) включает в себя поддержку для отладки интерфейса.

- [CAtlModule](../atl/reference/catlmodule-class.md) следующие `CAtlModule`-производные классы настраиваются так, чтобы содержать данные, необходимые в конкретным типом приложения. Большинство участников в эти классы можно переопределить:

   - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) используется в приложениях библиотеки DLL. Предоставляет код для стандартный экспорт.

   - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) используется в EXE-приложения. Предоставляет код, необходимый в EXE-файла.

   - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) обеспечивает поддержку для создания Windows NT и Windows 2000 служб.

`CComModule` по-прежнему доступен для обеспечения обратной совместимости.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>Причины для распространения функциональности CComModule

Функциональные возможности `CComModule` распространялось в несколько новых классов по следующим причинам:

- Возможности в `CComModule` детализированные.

   Поддержка для COM, работы с окнами, интерфейс отладки и функций конкретного приложения (DLL или EXE) теперь доступна в отдельные классы.

- Автоматически объявите глобальный экземпляр каждого из этих модулей.

   Глобальный экземпляр класса требуемый модуль связан в проект.

- Устраняют методов Init и термин.

   Методы init и термин перешло в конструкторы и деструкторы классов модуля; больше не нужно вызвать Init и термин.

## <a name="see-also"></a>См. также

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Общие сведения о классе](../atl/atl-class-overview.md)
