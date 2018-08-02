---
title: Структура CloakedIid | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3e0155006987165f5b192aac73bb31991081a231
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39461227"
---
# <a name="cloakediid-structure"></a>CloakedIid - структура
Указывает `RuntimeClass`, `Implements` и `ChainInterfaces` шаблоны, что заданный интерфейс недоступен в списке IID.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Параметры  
 *T*  
 Интерфейс, который является скрытым (замаскированные).  
  
## <a name="remarks"></a>Примечания  
 Ниже приведен пример того, как `CloakedIid` используется: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)