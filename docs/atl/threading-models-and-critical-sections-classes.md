---
title: Потоковых моделей и критических разделов классов (ATL)
ms.date: 11/04/2016
helpviewer_keywords:
- ATL, critical sections
- ATL, multithreading
- threading [ATL], models
- critical sections
ms.assetid: 759f05ef-6285-4be6-a2cc-78572dd75146
ms.openlocfilehash: 98db15a1fee2637b9493b538468fa9446015404f
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62196159"
---
# <a name="threading-models-and-critical-sections-classes"></a>Потоковых моделей и критических разделов классы

Следующие классы определяют потоковая модель и критического раздела:

- [CAtlAutoThreadModule](../atl/reference/catlautothreadmodule-class.md) реализует COM-сервера пула потоков, модель с подразделением.

- [CAtlAutoThreadModuleT](../atl/reference/catlautothreadmodulet-class.md) предоставляет методы для реализации пула потоков, модель с подразделением COM-сервера.

- [CComMultiThreadModel](../atl/reference/ccommultithreadmodel-class.md) предоставляет поточно ориентированные методы для увеличение и уменьшение переменной. Предоставляет критический раздел.

- [CComMultiThreadModelNoCS](../atl/reference/ccommultithreadmodelnocs-class.md) предоставляет поточно ориентированные методы для увеличение и уменьшение переменной. Не поддерживает критической секции.

- [CComSingleThreadModel](../atl/reference/ccomsinglethreadmodel-class.md) предоставляет методы для увеличение и уменьшение переменной. Не поддерживает критической секции.

- [CComObjectThreadModel](../atl/reference/atl-typedefs.md#ccomobjectthreadmodel) определяет соответствующий класс модель потоков для одного объекта класса.

- [CComGlobalsThreadModel](../atl/reference/atl-typedefs.md#ccomglobalsthreadmodel) определяет соответствующий класс потоковая модель для объекта, доступная по всему миру.

- [CComAutoCriticalSection](../atl/reference/ccomautocriticalsection-class.md) содержит методы получения и освобождения критического раздела. Автоматически инициализируется критический раздел.

- [CComCriticalSection](../atl/reference/ccomcriticalsection-class.md) содержит методы получения и освобождения критического раздела. Критический раздел необходимо инициализировать явным образом.

- [CComFakeCriticalSection](../atl/reference/ccomfakecriticalsection-class.md) отражает методы `CComCriticalSection` без предоставления критической секции. Методы в `CComFakeCriticalSection` ничего не делать.

- [CRTThreadTraits](../atl/reference/crtthreadtraits-class.md) предоставляет функцию создания потока CRT. Этот класс используется в том случае, если поток будет использовать функции CRT.

- [Win32ThreadTraits](../atl/reference/win32threadtraits-class.md) предоставляет функцию создания для потока Windows. Этот класс используется в том случае, если поток не будет использовать функции CRT.

## <a name="see-also"></a>См. также

[Общие сведения о классе](../atl/atl-class-overview.md)
