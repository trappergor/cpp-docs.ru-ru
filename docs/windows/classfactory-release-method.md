---
title: Метод ClassFactory::Release | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ClassFactory::Release
dev_langs:
- C++
helpviewer_keywords:
- Release method
ms.assetid: 49da2002-f9d6-4d7f-8a65-48c20b1bf99f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 293c95bb95feb1fa021fa742a90939c6680e7b0d
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39460645"
---
# <a name="classfactoryrelease-method"></a>Метод ClassFactory::Release
Уменьшает счетчик ссылок для текущего **ClassFactory** объекта.  
  
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
 [Класс ClassFactory](../windows/classfactory-class.md)