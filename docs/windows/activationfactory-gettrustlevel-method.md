---
title: Метод ActivationFactory::GetTrustLevel | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::GetTrustLevel
dev_langs:
- C++
helpviewer_keywords:
- GetTrustLevel method
ms.assetid: 31547ae6-d2ab-4039-923c-154d53fb1a8b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1e4dfbfbc146663722eba1302b27e96812d684f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="activationfactorygettrustlevel-method"></a>Метод ActivationFactory::GetTrustLevel
Возвращает объект, который создает экземпляр текущего ActivationFactory уровень доверия.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   GetTrustLevel  
)(_Out_ TrustLevel* trustLvl);  
```  
  
#### <a name="parameters"></a>Параметры  
 `trustLvl`  
 После завершения операции, уровень доверия класса среды выполнения, который создает экземпляры ActivationFactory.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае выдается ошибка утверждения и `trustLvl` равно FullTrust.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)