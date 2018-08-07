---
title: Метод Module::GetActivationFactory | Документация Майкрософт
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
ms.openlocfilehash: e41b90ea56f65665ccdaff0fe4dceff292d1cdcf
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39608109"
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
  
### <a name="parameters"></a>Параметры  
 *pActivatibleClassId*  
 Представляет IID класса среды выполнения.  
  
 *ppIFactory*  
 Представляет интерфейс IActivationFactory указанного класса среды выполнения.  
  
 *Имя_сервера*  
 Имя подмножества фабрик класса в текущем модуле. Укажите имя сервера, используемое в [ActivatableClassWithFactoryEx](../windows/activatableclass-macros.md) макрос, или указать **nullptr** для получения имени сервера по умолчанию.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, возвращаемое GetActivationFactory.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс Module](../windows/module-class.md)  
 [Макрос ActivatableClass](../windows/activatableclass-macros.md)