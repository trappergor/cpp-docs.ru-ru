---
title: Класс SimpleClassFactory | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleClassFactory
dev_langs:
- C++
helpviewer_keywords:
- SimpleClassFactory class
ms.assetid: 6edda1b2-4e44-4e14-9364-72f519249962
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: debb78ba4be2731b8cffce1133518b0b4a04f63d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892765"
---
# <a name="simpleclassfactory-class"></a>SimpleClassFactory - класс
Предоставляет основной механизм для создания базового класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename Base>  
class SimpleClassFactory : public ClassFactory<>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Базовый класс.  
  
## <a name="remarks"></a>Примечания  
 Базовый класс должен предоставлять конструктор по умолчанию.  
  
 В следующем примере кода демонстрируется использование SimpleClassFactory с [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос.  
  
 `ActivatableClassWithFactoryEx(MyClass, SimpleClassFactory, MyServerName);`  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод SimpleClassFactory::CreateInstance](../windows/simpleclassfactory-createinstance-method.md)|Создает экземпляр указанного интерфейса.|  
  
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
  
 `ClassFactory`  
  
 `SimpleClassFactory`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)