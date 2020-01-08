---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: 37bb7a8c7fef963f340704561e24e33cc36707f3
ms.sourcegitcommit: a5fa9c6f4f0c239ac23be7de116066a978511de7
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/20/2019
ms.locfileid: "75298640"
---
# <a name="queryinterface"></a>QueryInterface

Хотя существуют механизмы, с помощью которых объект может выразить функциональность, которую он предоставляет статически (перед созданием экземпляра), основной механизм COM заключается в использовании метода `IUnknown` с именем [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q)).

Каждый интерфейс является производным от `IUnknown`, поэтому каждый интерфейс имеет реализацию `QueryInterface`. Независимо от реализации этот метод запрашивает объект, используя идентификатор IID интерфейса, которому вызывающему объекту требуется указатель. Если объект поддерживает этот интерфейс, `QueryInterface` получает указатель на интерфейс, а также вызывает `AddRef`. В противном случае возвращается код ошибки E_NOINTERFACE.

Обратите внимание, что всегда необходимо соблюдать правила [подсчета ссылок](../atl/reference-counting.md) . Если вы вызываете `Release` для указателя интерфейса, чтобы уменьшить значение счетчика ссылок до нуля, не следует использовать этот указатель еще раз. Иногда может потребоваться получить слабую ссылку на объект (то есть может понадобиться получить указатель на один из его интерфейсов, не увеличивая число ссылок), но это неприемлемо для этого путем вызова `QueryInterface`, за которым следует `Release`. Указатель, полученный таким образом, является недопустимым и не должен использоваться. Это становится очевидным при определении [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) , поэтому определение этого макроса является удобным способом поиска ошибок подсчета ссылок.

## <a name="see-also"></a>См. также:

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[QueryInterface: Навигация в объекте](/windows/win32/com/queryinterface--navigating-in-an-object)
