---
title: Класс CAtlAutoThreadModule | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlAutoThreadModule
- atlbase/ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 9c89d142254909591ebd01bfa859be5488cbfaf6
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32356622"
---
# <a name="catlautothreadmodule-class"></a>Класс CAtlAutoThreadModule
Этот класс реализует пула потоков, модели подразделения COM-сервера.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Примечания  
 `CAtlAutoThreadModule` является производным от [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) и реализует пула потоков, модели подразделения COM-сервера. `CAtlAutoThreadModule` использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления подразделениями для каждого потока в модуле.  
  
 Необходимо использовать [DECLARE_CLASSFACTORY_AUTO_THREAD](aggregation-and-class-factory-macros.md#declare_classfactory_auto_thread) макроса в определении класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса. Затем следует добавить экземпляр класса, производного от `CAtlAutoThreadModuleT` например `CAtlAutoThreadModule`. Пример:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Этот класс заменяет устаревшее [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) класса.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IAtlAutoThreadModule`  
  
 [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)  
  
 `CAtlAutoThreadModule`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="see-also"></a>См. также  
 [Класс CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md)   
 [Класс IAtlAutoThreadModule](../../atl/reference/iatlautothreadmodule-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Классы модуля](../../atl/atl-module-classes.md)
