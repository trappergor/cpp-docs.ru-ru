---
title: Несколько сдвоенных интерфейсов
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- multiple dual interfaces
- COM_INTERFACE_ENTRY2 macro
- dual interfaces, exposing multiple
- multiple dual interfaces, exposing with ATL
- IDispatchImpl class, multiple dual interfaces
- COM_INTERFACE_ENTRY_IID macro
ms.assetid: 7fea86e6-247f-4063-be6e-85588a9e3719
ms.openlocfilehash: 2ed0e9e8c74e02917e852b8f95ebff1b048afaef
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62261583"
---
# <a name="multiple-dual-interfaces"></a>Несколько сдвоенных интерфейсов

Вы можете сочетать преимущества сдвоенный интерфейс (то есть гибкость vtable и позднее связывание, таким образом сделать класс доступным для языков сценариев, как и C++) с использованием множественное наследование.

Несмотря на то, что возможность предоставлять доступ к несколько сдвоенных интерфейсов с одним объектом COM, не рекомендуется. Если есть несколько сдвоенных интерфейсов, должен содержать только один `IDispatch` интерфейса, предоставленного. Методы, чтобы гарантировать, что это происходит выполнение штрафов утрата функции или кода повышенной сложности. Разработчик, учитывая этот подход следует тщательно взвесить преимущества и недостатки.

## <a name="exposing-a-single-idispatch-interface"></a>Предоставляя единый интерфейс IDispatch

Можно предоставить несколько сдвоенных интерфейсов одного объекта путем наследования от двух или более специализации `IDispatchImpl`. Тем не менее если вы позволяете клиентам запрашивать `IDispatch` интерфейс, необходимо будет использовать [COM_INTERFACE_ENTRY2](reference/com-interface-entry-macros.md#com_interface_entry2) макрос (или [COM_INTERFACE_ENTRY_IID](reference/com-interface-entry-macros.md#com_interface_entry_iid))) для указания какой базовый класс, используемый для Реализация `IDispatch`.

[!code-cpp[NVC_ATL_COM#23](../atl/codesnippet/cpp/multiple-dual-interfaces_1.h)]

Так как только один `IDispatch` интерфейс предоставляется, клиенты, которые доступны только через объекты `IDispatch` интерфейс не смогут получить доступ к методу или свойству в любом другом интерфейсе.

## <a name="combining-multiple-dual-interfaces-into-a-single-implementation-of-idispatch"></a>Объединение нескольких сдвоенные интерфейсы в одной реализации интерфейса IDispatch

ATL не предоставляет поддержку объединения несколько сдвоенных интерфейсов в единую реализацию `IDispatch`. Тем не менее, существует несколько известных подходов вручную вместо объединения интерфейсов, таких как создание шаблонного класса, который содержит объединение отдельных `IDispatch` интерфейсы, создание объекта для выполнения `QueryInterface` , или с помощью Реализация на основе typeInfo вложенных объектов для создания `IDispatch` интерфейс.

Эти подходы имеют проблемы с потенциальные конфликты имен, а также сложность кода и удобство поддержки. Не рекомендуется создавать несколько сдвоенных интерфейсов.

## <a name="see-also"></a>См. также

[Сдвоенные интерфейсы и ATL](../atl/dual-interfaces-and-atl.md)
