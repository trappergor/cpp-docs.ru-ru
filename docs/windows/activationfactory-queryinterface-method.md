---
title: Метод ActivationFactory::QueryInterface | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::ActivationFactory::QueryInterface
dev_langs:
- C++
helpviewer_keywords:
- QueryInterface method
ms.assetid: 2a9b71aa-61c0-43f7-aa35-00f0ee0af031
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a2ed2393f25dac416cf3b6dfd1b178190d368a6
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39647106"
---
# <a name="activationfactoryqueryinterface-method"></a>Метод ActivationFactory::QueryInterface
Извлекает указатель на указанный интерфейс.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
STDMETHOD(  
   QueryInterface  
)(REFIID riid, _Deref_out_ void **ppvObject);  
```  
  
### <a name="parameters"></a>Параметры  
 *riid*  
 Идентификатор интерфейса.  
  
 *ppvObject*  
 Когда эта операция будет завершена, указатель на интерфейс, заданный параметром *riid*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ActivationFactory](../windows/activationfactory-class.md)