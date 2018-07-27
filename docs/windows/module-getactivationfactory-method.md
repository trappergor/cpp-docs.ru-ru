---
title: Метод Module::GetActivationFactory | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Module::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory method
ms.assetid: 59da8844-072e-414b-b89c-1db1cc4fd81d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 837cb68173ca1994de6bc560882d617bb3aa03e0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33887017"
---
# <a name="modulegetactivationfactory-method"></a>Метод Module::GetActivationFactory
Получает фабрику активации для модуля.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW HRESULT GetActivationFactory(  
   _In_ HSTRING pActivatibleClassId,  
   _Deref_out_ IActivationFactory **ppIFactory,  
   wchar_t* serverName = nullptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `pActivatibleClassId`  
 Представляет IID класса среды выполнения.  
  
 `ppIFactory`  
 Представляет интерфейс IActivationFactory указанного класса среды выполнения.  
  
 `serverName`  
 Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос, или укажите `nullptr` для получения имени сервера по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
[Класс модуля](../windows/module-class.md) [макрос Activatableclass](../windows/activatableclass-macros.md)