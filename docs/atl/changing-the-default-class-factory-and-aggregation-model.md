---
title: Изменение статистической модели и фабрики класса по умолчанию | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
dev_langs:
- C++
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ce64f2162aa0d5cdf5bcf5e16b56b6989fcaf1ee
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32355243"
---
# <a name="changing-the-default-class-factory-and-aggregation-model"></a>Изменение статистической модели и фабрики класса по умолчанию
ATL использует [CComCoClass](../atl/reference/ccomcoclass-class.md) для определения модели по умолчанию класс фабрики и статистической обработки для объекта. `CComCoClass` Задает следующие два макроса:  
  
-   [DECLARE_CLASSFACTORY](reference/aggregation-and-class-factory-macros.md#declare_classfactory) объявляет фабрики класса, чтобы быть [CComClassFactory](../atl/reference/ccomclassfactory-class.md).  
  
-   [DECLARE_AGGREGATABLE](reference/aggregation-and-class-factory-macros.md#declare_aggregatable) объявляет, что объект может быть статистически вычислена.  
  
 Одно из этих значений по умолчанию можно переопределить, указав другой макроса в определении класса. Например, чтобы использовать [CComClassFactory2](../atl/reference/ccomclassfactory2-class.md) вместо `CComClassFactory`, укажите [DECLARE_CLASSFACTORY2](reference/aggregation-and-class-factory-macros.md#declare_classfactory2) макрос:  
  
 [!code-cpp[NVC_ATL_COM#2](../atl/codesnippet/cpp/changing-the-default-class-factory-and-aggregation-model_1.h)]  
  
 Два других макроса, которые определяют фабрики класса являются [DECLARE_CLASSFACTORY_AUTO_THREAD](reference/aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) и [DECLARE_CLASSFACTORY_SINGLETON](reference/aggregation-and-class-factory-macros.md#declare_classfactory_singleton).  
  
 Также использует ATL `typedef` механизм для реализации поведения по умолчанию. Например `DECLARE_AGGREGATABLE` использует макрос `typedef` , чтобы определить тип с именем **_CreatorClass**, который затем есть ссылка во всей библиотеки ATL. Обратите внимание, что в производном классе, `typedef` тем же именем, как базовый класс `typedef` приводит к ATL с помощью вашего определения и переопределение поведения по умолчанию.  
  
## <a name="see-also"></a>См. также  
 [Основные принципы работы COM-объекты ATL](../atl/fundamentals-of-atl-com-objects.md)   
 [Макросы агрегирования и фабрик классов](../atl/reference/aggregation-and-class-factory-macros.md)

