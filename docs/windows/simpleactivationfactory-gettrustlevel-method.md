---
title: Метод SimpleActivationFactory::GetTrustLevel | Документы Microsoft
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
ms.openlocfilehash: b08ce574a8370eb0029a702f8fa4a4b12c6e93c1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892622"
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