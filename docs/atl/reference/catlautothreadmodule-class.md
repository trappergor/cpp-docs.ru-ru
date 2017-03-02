---
title: "Класс CAtlAutoThreadModule | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CAtlAutoThreadModule
- CAtlAutoThreadModule
- ATL::CAtlAutoThreadModule
dev_langs:
- C++
helpviewer_keywords:
- CAtlAutoThreadModule class
ms.assetid: 3be834aa-55ef-403e-94ae-41979691b15f
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 09f4a7061ce1e4a09d0d27bd90dfcc16a37f4d5b
ms.lasthandoff: 02/24/2017

---
# <a name="catlautothreadmodule-class"></a>Класс CAtlAutoThreadModule
Этот класс реализует пул потоков, модели подразделения COM-сервера.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlAutoThreadModule : public CAtlAutoThreadModuleT<CAtlAutoThreadModule>
```  
  
## <a name="remarks"></a>Примечания  
 `CAtlAutoThreadModule`является производным от [CAtlAutoThreadModuleT](../../atl/reference/catlautothreadmodulet-class.md) и реализует пул потоков, модели подразделения COM-сервера. `CAtlAutoThreadModule`использует [CComApartment](../../atl/reference/ccomapartment-class.md) для управления подразделениями для каждого потока в модуле.  
  
 Необходимо использовать [DECLARE_CLASSFACTORY_AUTO_THREAD](http://msdn.microsoft.com/library/19d7105e-03e8-4412-9f5e-5384c8a5e18f) макрос в определении класса объекта, чтобы указать [CComClassFactoryAutoThread](../../atl/reference/ccomclassfactoryautothread-class.md) как фабрика класса. Затем следует добавить экземпляр класса, производного от `CAtlAutoThreadModuleT` такие как `CAtlAutoThreadModule`. Например:  
  
 `CAtlAutoThreadModule _AtlAutoModule; // name is immaterial.`  
  
> [!NOTE]
>  Этот класс заменяет устаревшие [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) класса.  
  
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
