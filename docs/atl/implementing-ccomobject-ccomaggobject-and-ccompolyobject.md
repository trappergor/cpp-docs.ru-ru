---
title: Реализация CComObject, CComAggObject и CComPolyObject | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: conceptual
f1_keywords:
- CComPolyObject
- CComAggObject
- CComObject
dev_langs:
- C++
helpviewer_keywords:
- CComPolyObject class, implementing
- CreateInstance method
- CComAggObject class
- CComObject class, implementing
ms.assetid: 5aabe938-104d-492e-9c41-9f7fb1c62098
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5ac45a6edbe606ba445ed3ae58cfde348f83e4de
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="implementing-ccomobject-ccomaggobject-and-ccompolyobject"></a>Реализация CComObject, CComAggObject и CComPolyObject
Классы шаблонов [CComObject](../atl/reference/ccomobject-class.md), [CComAggObject](../atl/reference/ccomaggobject-class.md), и [CComPolyObject](../atl/reference/ccompolyobject-class.md) всегда являются наиболее производные классы в цепочке наследования. Обрабатывать все методы в их обязанность **IUnknown**: `QueryInterface`, `AddRef`, и **выпуска**. Кроме того `CComAggObject` и `CComPolyObject` (при использовании для объектов, статистические) предоставляют специальные подсчет ссылок на и `QueryInterface` семантику, необходимые для внутреннего unknown.  
  
 Ли `CComObject`, `CComAggObject`, или `CComPolyObject` используется зависит от того, объявляется один (или нет) следующие макросы:  
  
|Макрос|Действие|  
|-----------|------------|  
|`DECLARE_NOT_AGGREGATABLE`|Всегда использует `CComObject`.|  
|`DECLARE_AGGREGATABLE`|Использует `CComAggObject` Если объект является статистическим выражением и `CComObject` Если это не так. `CComCoClass` Этот макрос содержит, если ни одна из **DECLARE_\*_AGGREGATABLE** макросы объявлены в классе, используется по умолчанию.|  
|`DECLARE_ONLY_AGGREGATABLE`|Всегда использует `CComAggObject`. Возвращает ошибку, если объект не является статистическим выражением.|  
|`DECLARE_POLY_AGGREGATABLE`|ATL создает экземпляр **CComPolyObject\<окне отслеживания TRACE появляется >** при **IClassFactory::CreateInstance** вызывается. Во время создания проверяется значение внешняя Неизвестная строка. Если это **NULL**, **IUnknown** реализуется для неагрегированные объекта. Если внешняя Неизвестная строка не **NULL**, **IUnknown** реализуется для вычисляемого объекта.|  
  
 Преимущество использования `CComAggObject` и `CComObject` это реализация **IUnknown** оптимизирован для типа создаваемого объекта. Для экземпляра неагрегированные объект достаточно подсчет ссылок, пока объект агрегированных должен счетчик ссылок для внутреннего неизвестно и указатель на внешняя Неизвестная строка.  
  
 Преимущество использования `CComPolyObject` — избежать обладает и разрешением `CComAggObject` и `CComObject` в модуле для обработки случаев, статистические и нестатистические. Один `CComPolyObject` объект обрабатывает в обоих случаях. Это означает, что существуют только одна копия виртуальной таблице и одной копии функций в модуле. При большом вашей vtable это существенно уменьшить размер вашего модуля. Тем не менее, используемой при небольших вашей vtable `CComPolyObject` может привести к немного больший размер модуля, так как он не оптимизирован для суммирования или неагрегированные объекта, как `CComAggObject` и `CComObject`.  
  
## <a name="see-also"></a>См. также  
 [Основные принципы работы COM-объекты ATL](../atl/fundamentals-of-atl-com-objects.md)   
 [Макросы агрегирования и фабрик классов](../atl/reference/aggregation-and-class-factory-macros.md)

