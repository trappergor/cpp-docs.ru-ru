---
title: Модульные классы ATL | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 8e885ef1db8f282bbdca2e8c39c3d1221d791d1a
ms.sourcegitcommit: 913c3bf23937b64b90ac05181fdff3df947d9f1c
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 09/18/2018
ms.locfileid: "46067640"
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

