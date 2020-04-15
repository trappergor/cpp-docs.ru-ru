---
title: Модульные классы ATL
ms.date: 11/04/2016
helpviewer_keywords:
- CComModule class, what's changed
- ATL, module classes
- module classes
ms.assetid: fd75382d-c955-46ba-a38e-37728b7fa00f
ms.openlocfilehash: 2b72cac0da06b70a40e01fcc75da52f1678f3f64
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81317373"
---
# <a name="atl-module-classes"></a>Модульные классы ATL

Эта тема обсуждает классы модулей, которые были новыми в ATL 7.0.

## <a name="ccommodule-replacement-classes"></a>Классы замены CComModule

Более ранние версии ATL используется `CComModule`. В ATL 7.0 `CComModule` функциональность заменяется несколькими классами:

- [CAtlBaseМодуль](../atl/reference/catlbasemodule-class.md) Содержит информацию, требуемую большинством приложений, которые используют ATL. Содержит HINSTANCE модуля и экземпляр ресурса.

- [CAtlComModule](../atl/reference/catlcommodule-class.md) Содержит информацию, требуемую классами COM в ATL.

- [CAtlWinModule](../atl/reference/catlwinmodule-class.md) Содержит информацию, требуемую классами окон в ATL.

- [CAtlDebugИнтерфейсыМодуль](../atl/reference/catldebuginterfacesmodule-class.md) Содержит поддержку для отладки интерфейса.

- [CAtlModule](../atl/reference/catlmodule-class.md) Следующие `CAtlModule`классы, полученные из них, настроены таким образом, чтобы содержать информацию, требуемую в определенном типе приложения. Большинство участников этих классов могут быть переопределены:

  - [CAtlDllModuleT](../atl/reference/catldllmodulet-class.md) Используется в приложениях DLL. Предоставляет код для стандартного экспорта.

  - [CAtlExeModuleT](../atl/reference/catlexemodulet-class.md) Используется в приложениях EXE. Предоставляет код, необходимый в EXE.

  - [CAtlServiceModuleT](../atl/reference/catlservicemodulet-class.md) Предоставляет поддержку для создания служб Windows NT и Windows 2000.

`CComModule`по-прежнему доступна для обратной совместимости.

## <a name="reasons-for-distributing-ccommodule-functionality"></a>Причины для распространения функциональности CComModule

Функциональность была `CComModule` распределена по нескольким новым классам по следующим причинам:

- Сделать функциональность `CComModule` в гранулированной.

   Поддержка функций COM, windowing, интерфейса и приложений (DLL или EXE) теперь находится в отдельных классах.

- Автоматически объявлять глобальный экземпляр каждого из этих модулей.

   Глобальный экземпляр требуемых классов модулей связан с проектом.

- Удалите необходимость вызова Init и Термин а.

   Методы Init и Term перешли в конструкторы и деструкторы для классов модулей; больше нет необходимости называть Init и Term.

## <a name="see-also"></a>См. также раздел

[Основные понятия](../atl/active-template-library-atl-concepts.md)<br/>
[Общие сведения о классах](../atl/atl-class-overview.md)
