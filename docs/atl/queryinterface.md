---
title: QueryInterface
ms.date: 11/04/2016
ms.topic: reference
helpviewer_keywords:
- interfaces, pointers
- interfaces, availability
- QueryInterface method
ms.assetid: 62fce95e-aafa-4187-b50b-e6611b74c3b3
ms.openlocfilehash: de2762cff3d697261e159336d866a5a7cb10fafa
ms.sourcegitcommit: fcb48824f9ca24b1f8bd37d647a4d592de1cc925
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/15/2019
ms.locfileid: "69492007"
---
# <a name="queryinterface"></a>QueryInterface

Хотя существуют механизмы, с помощью которых объект может выразить функциональность, которую он предоставляет статически (перед созданием экземпляра), основной механизм com заключается в использовании метода с `IUnknown` именем [QueryInterface](/windows/win32/api/unknwn/nf-unknwn-iunknown-queryinterface(q_)).

Каждый интерфейс является производным `IUnknown`от, поэтому каждый интерфейс имеет `QueryInterface`реализацию. Независимо от реализации этот метод запрашивает объект, используя идентификатор IID интерфейса, которому вызывающему объекту требуется указатель. Если объект поддерживает этот интерфейс, `QueryInterface` получает указатель на интерфейс, а также вызывает. `AddRef` В противном случае возвращается код ошибки E_NOINTERFACE.

Обратите внимание, что всегда необходимо соблюдать правила подсчета [ссылок](../atl/reference-counting.md) . Если вы вызываете `Release` указатель интерфейса, чтобы уменьшить значение счетчика ссылок до нуля, не следует использовать этот указатель еще раз. Иногда может потребоваться получить слабую ссылку на объект (то есть может понадобиться получить указатель на один из его интерфейсов, не увеличивая счетчик ссылок), но это неприемлемо для этого, вызвав `QueryInterface` , `Release`за которым следует. Указатель, полученный таким образом, является недопустимым и не должен использоваться. Это становится очевидным, если определен [_ATL_DEBUG_INTERFACES](reference/debugging-and-error-reporting-macros.md#_atl_debug_interfaces) , поэтому определение этого макроса является удобным способом поиска ошибок подсчета ссылок.

## <a name="see-also"></a>См. также

[Введение в модель COM](../atl/introduction-to-com.md)<br/>
[QueryInterface Перемещение по объекту](/windows/win32/com/queryinterface--navigating-in-an-object)
