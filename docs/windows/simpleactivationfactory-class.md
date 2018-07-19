---
title: Класс SimpleActivationFactory | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleActivationFactory class
ms.assetid: aff768e0-0038-4fd7-95d2-ad7d308da41c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2d10544a08fa6faebb1434cd00ca80ac30d4570a
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889852"
---
# <a name="simpleactivationfactory-class"></a>SimpleActivationFactory - класс
Предоставляет основной механизм для создания базового класса среды выполнения Windows или классической модели COM.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Base>  
class SimpleActivationFactory : public ActivationFactory<>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Базовый класс.  
  
## <a name="remarks"></a>Примечания  
 Базовый класс должен предоставлять конструктор по умолчанию.  
  
 В следующем примере кода демонстрируется использование SimpleActivationFactory с [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleActivationFactory, MyServerName);`  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SimpleActivationFactory::ActivateInstance](../windows/simpleactivationfactory-activateinstance-method.md)|Создает экземпляр указанного интерфейса.|  
|[Метод SimpleActivationFactory::GetRuntimeClassName](../windows/simpleactivationfactory-getruntimeclassname-method.md)|Получает имя класса среды выполнения экземпляра класса, указанного в параметре шаблона класса `Base`.|  
|[Метод SimpleActivationFactory::GetTrustLevel](../windows/simpleactivationfactory-gettrustlevel-method.md)|Возвращает уровень доверия экземпляра класса, указанного параметром `Base` параметре шаблона класса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `ActivationFactory`  
  
 `SimpleActivationFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)