---
title: "Метод SimpleActivationFactory::GetTrustLevel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::SimpleActivationFactory::GetTrustLevel
dev_langs:
- C++
ms.assetid: 99aa9bc9-d954-4a6f-902b-4abe00e43039
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 608f67267b8a82341ff3beb3e27f8e0eb9891c8a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>Метод SimpleActivationFactory::GetTrustLevel
Возвращает уровень доверия экземпляра класса, указанного параметром `Base` параметре шаблона класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Параметры  
 `trustLvl`  
 После завершения операции уровня доверия для текущего объекта класса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Всегда возвращает значение S_OK.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс SimpleActivationFactory](../windows/simpleactivationfactory-class.md)