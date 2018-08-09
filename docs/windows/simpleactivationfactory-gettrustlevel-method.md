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
ms.openlocfilehash: 1234c667426937f5d40937c5f2bcc72949e827ae
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40012398"
---
# <a name="simpleactivationfactorygettrustlevel-method"></a>Метод SimpleActivationFactory::GetTrustLevel
Получает уровень доверия выполняемого экземпляра класса, указанного параметром `Base` параметре шаблона класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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