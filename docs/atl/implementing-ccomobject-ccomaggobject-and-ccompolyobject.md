---
title: Реализация CComObject, CComAggObject и CComPolyObject
ms.date: 11/04/2016
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
ms.openlocfilehash: 6e9e1a22ebe23f9fec6e553713a5701315cdac96
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50508983"
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>Реализация CComObject, CComAggObject и CComPolyObject

Классы шаблонов [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), и [CComPolyObject](../atl/reference/ccompolyobject-class.md) всегда являются наиболее производные классы в цепочке наследования. Отвечает за их обрабатывать все методы в `IUnknown`: `QueryInterface`, `AddRef`, и `Release`. Кроме того `CComAggObject` и `CComPolyObject` (при использовании для агрегированных объектов) предоставляют специальные подсчетом и `QueryInterface` семантику, необходимые для внутреннего unknown.

Ли `CComObject`, `CComAggObject`, или `CComPolyObject` используется зависит ли объявить один (или none) из следующих макросов:

|Макрос|Действие|
|-----------|------------|
|DECLARE_NOT_AGGREGATABLE|Всегда использует `CComObject`.|
|DECLARE_AGGREGATABLE|Использует `CComAggObject` Если объект является статистическим и `CComObject` Если это не так. `CComCoClass` содержит этот макрос, если ни одна из DECLARE_ * _AGGREGATABLE макросы объявляются в классе, это будет по умолчанию.|
|DECLARE_ONLY_AGGREGATABLE|Всегда использует `CComAggObject`. Возвращает ошибку, если объект не является агрегатом.|
|DECLARE_POLY_AGGREGATABLE|ATL создает экземпляр класса **CComPolyObject\<окне отслеживания TRACE появляется >** при `IClassFactory::CreateInstance` вызывается. Во время создания проверяется значение внешняя Неизвестная строка. Если он равен NULL, `IUnknown` реализуется для объекта неагрегированные. Если внешняя Неизвестная строка не равно NULL, `IUnknown` реализуется для объединенного объекта.|

Преимущество использования `CComAggObject` и `CComObject` том, что реализация `IUnknown` оптимизирован для типа создаваемого объекта. Например объект неагрегированные достаточно подсчет ссылок, хотя объединенного объекта должен счетчик ссылок для внутреннего неизвестного и указатель на внешняя Неизвестная строка.

Преимущество использования `CComPolyObject` — избежать обеих `CComAggObject` и `CComObject` в модуле для обработки вариантов, статистические и неагрегированные. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что только одна копия таблицы vtable и одна копия функции существуют в модуле. Если в таблице vtable имеет большой размер, это может значительно снизить размер вашего модуля. Тем не менее, если в таблице vtable невелик, с помощью `CComPolyObject` может привести к немного больший размер модуля, поскольку метод не оптимизирован для суммирования или неагрегированные объекта, так как `CComAggObject` и `CComObject`.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Макросы агрегирования и фабрик классов](../atl/reference/aggregation-and-class-factory-macros.md)

