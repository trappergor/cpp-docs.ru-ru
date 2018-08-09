---
title: Метод SimpleActivationFactory::GetTrustLevel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 22fa30a3662897b171245da194573ec17da2f64e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39645192"
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>Метод SimpleActivationFactory::GetTrustLevel
Получает уровень доверия выполняемого экземпляра класса, указанного параметром `Base` параметре шаблона класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
### <a name="parameters"></a>Параметры  
 *trustLvl*  
 После завершения операции, уровень доверия текущего объекта класса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)