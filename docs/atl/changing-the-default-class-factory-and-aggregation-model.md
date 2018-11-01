---
title: Изменение модели агрегирования и фабрики класса по умолчанию
ms.date: 11/04/2016
helpviewer_keywords:
- CComClassFactory class, making the default
- aggregation [C++], using ATL
- aggregation [C++], aggregation models
- defaults [C++], aggregation model in ATL
- default class factory
- class factories, changing default
- CComCoClass class, default class factory and aggregation model
- default class factory, ATL
- defaults [C++], class factory
ms.assetid: 6e040e95-0f38-4839-8a8b-c9800dd47e8c
ms.openlocfilehash: 34e838eea201f96acd7dcc647c4410fb244c8424
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485557"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Изменение модели агрегирования и фабрики класса по умолчанию

Использует ATL [CComCoClass](../atl/reference/ccomcoclass-class.md) для определения модели по умолчанию класс фабрики и статистическую обработку для объекта. `CComCoClass` Задает следующие два макроса:

- [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) объявляет фабрики класса быть [CComClassFactory](../atl/reference/ccomclassfactory-class.md).

- [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) объявляет, что объект может быть агрегировано.

Одно из этих умолчаний можно переопределить, указав другой макроса в определении класса. Например, чтобы использовать [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) макрос:

[!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]

Два других макроса, которые определяют фабрику класса являются [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) и [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).

ATL также использует **typedef** механизм для реализации поведения по умолчанию. Например, используется макрос DECLARE_AGGREGATABLE **typedef** определить тип с именем `_CreatorClass`, который затем ссылка на протяжении всего ATL. Обратите внимание, что в производном классе, **typedef** тем же именем, как базовый класс **typedef** приводит ATL с помощью определения и переопределение поведения по умолчанию.

## <a name="see-also"></a>См. также

[Основы COM-объектов ATL](../atl/fundamentals-of-atl-com-objects.md)<br/>
[Макросы агрегирования и фабрик классов](../atl/reference/aggregation-and-class-factory-macros.md)

