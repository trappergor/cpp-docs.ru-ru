---
title: Константа ChainInterfaces::IidCount | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::IidCount
dev_langs:
- C++
helpviewer_keywords:
- IidCount constant
ms.assetid: d4a90aa0-513c-4e99-b978-e12149734936
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6d089e9639d83150e501b32577de94fc43b516c1
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463945"
---
# <a name="chaininterfacesiidcount-constant"></a>Константа ChainInterfaces::IidCount
Общее количество содержащихся в интерфейсах, указанные параметрами шаблона идентификаторы интерфейсов *I0* через *I9*.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
static const unsigned long IidCount = Details::InterfaceTraits<I0>::IidCount + Details::InterfaceTraits<I1>::IidCount + Details::InterfaceTraits<I2>::IidCount + Details::InterfaceTraits<I3>::IidCount + Details::InterfaceTraits<I4>::IidCount + Details::InterfaceTraits<I5>::IidCount + Details::InterfaceTraits<I6>::IidCount + Details::InterfaceTraits<I7>::IidCount + Details::InterfaceTraits<I8>::IidCount + Details::InterfaceTraits<I9>::IidCount;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Общее число идентификаторов интерфейса.  
  
## <a name="remarks"></a>Примечания  
 Параметры шаблона *I0* и *I1* являются обязательными и параметры *I2* через *I9* являются необязательными. Количество каждого интерфейса IID обычно равно 1.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)