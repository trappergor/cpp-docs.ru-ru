---
title: Реализация CComObjectRootEx
ms.date: 11/04/2016
helpviewer_keywords:
- CComObjectRoot class, implementing
- CComObjectRootEx class
ms.assetid: 79630c44-f2df-4e9e-b730-400a0ebfbd2b
ms.openlocfilehash: 80ce9936546b936770d8dedd0ba55f8c05617d37
ms.sourcegitcommit: 8105b7003b89b73b4359644ff4281e1595352dda
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/14/2019
ms.locfileid: "57809760"
---
# <a name="implementing-ccomobjectrootex"></a>Реализация CComObjectRootEx

[CComObjectRootEx](../atl/reference/ccomobjectrootex-class.md) необходим; все объекты ATL должны иметь один экземпляр `CComObjectRootEx` или [CComObjectRoot](../atl/reference/ccomobjectroot-class.md) в своем наследовании. `CComObjectRootEx` предоставляет механизм по умолчанию `QueryInterface`, основанный на записях сопоставления COM.

Посредством его сопоставления COM интерфейсы объекта предоставляются клиенту, когда он запрашивает интерфейс. Запрос выполняется с помощью `CComObjectRootEx::InternalQueryInterface`. `InternalQueryInterface` обрабатывает интерфейсы только в таблице сопоставлений COM.

Вы можете ввести интерфейсы в таблицу сопоставлений COM с [COM_INTERFACE_ENTRY](reference/com-interface-entry-macros.md#com_interface_entry) макрос или одного из его вариантов. Например, следующий код вводит интерфейсы `IDispatch`, `IBeeper` и `ISupportErrorInfo` в таблицу сопоставлений COM:

[!code-cpp[NVC_ATL_COM#1](../atl/codesnippet/cpp/implementing-ccomobjectrootex_1.h)]

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Макросы сопоставления COM](../atl/reference/com-map-macros.md)
