---
title: Метод ActivationFactory::Release | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 5bc25ff0-ee3c-4a2d-a9b6-2d8f158033ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e3f05576b4122acd21f7a535172a1facd562ed4
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39466391"
---
# <a name="activationfactoryrelease-method"></a>Метод ActivationFactory::Release
Уменьшает счетчик ссылок текущего **ActivationFactory** объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD_(  
   ULONG,  
   Release  
)();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)