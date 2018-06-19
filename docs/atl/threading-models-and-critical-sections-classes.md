---
title: Работа с потоками моделей и критические секции классов (ATL) | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- vc.atl.threads.models
dev_langs:
- C++
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 37172c0080664f496bdf5d5c7c0ebecbd8f77898
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359922"
---
# <a name="threading-models-and-critical-sections-classes"></a>Работа с потоками моделей и классы критические секции
Следующие классы определяют потоковой модели и критический раздел:  
  
-   [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) реализует пула потоков, модели подразделения COM-сервера.  
  
-   [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) предоставляет методы для реализации пула потоков, модели подразделения COM-сервера.  
  
-   [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) предоставляет методы поточно ориентированного увеличивать и уменьшать переменной. Предоставляет критической секции.  
  
-   [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) предоставляет методы поточно ориентированного увеличивать и уменьшать переменной. Не поддерживает критической секции.  
  
-   [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) предоставляет методы для увеличение и уменьшение переменной. Не поддерживает критической секции.  
  
-   [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) определяет соответствующего класса потоковая модель для одного объекта класса.  
  
-   [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) определяет соответствующего класса потоковая модель для объекта, который будет доступно.  
  
-   [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) содержит методы для получения и освобождения критической секции. Автоматически инициализируется критической секции.  
  
-   [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) содержит методы для получения и освобождения критической секции. Критическая секция должна быть инициализирована явно.  
  
-   [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) отражает методы в `CComCriticalSection` без предоставления критической секции. Методы в `CComFakeCriticalSection` не выполняют никаких действий.  
  
-   [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) предоставляет функции создания потока CRT. Этот класс используется в том случае, если поток будет использовать функции CRT.  
  
-   [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) предоставляет функции создания для потока Windows. Этот класс используется в том случае, если поток не будет использовать функции CRT.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../atl/atl-class-overview.md)

