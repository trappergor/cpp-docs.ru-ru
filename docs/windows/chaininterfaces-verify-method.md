---
title: Метод ChainInterfaces::Verify | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs:
- C++
helpviewer_keywords:
- Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b71581687ec69a4aff85f649e85ebfe10c0a844f
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39650473"
---
# <a name="chaininterfacesverify-method"></a>Метод ChainInterfaces::Verify
Проверяет, что каждому интерфейсу, определяемая параметрами шаблона *I0* через *I9* наследует от `IUnknown` и/или `IInspectable`и что *I0* наследует от *I1* через *I9*.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Примечания  
 При сбое операции проверки **static_assert** выдает сообщение об ошибке, описывающее ошибку.  
  
## <a name="remarks"></a>Примечания  
 Параметры шаблона *I0* и *I1* являются обязательными и параметры *I2* через *I9* являются необязательными.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)