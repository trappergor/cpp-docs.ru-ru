---
title: "Функция ActivationFactoryCallback | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::ActivationFactoryCallback
dev_langs:
- C++
helpviewer_keywords:
- ActivationFactoryCallback function
ms.assetid: dd40c79b-1273-4f2a-8c24-ae9926fb4fd9
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e88a6f9cb89746cd0380587789fbdd68f80d5e36
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="activationfactorycallback-function"></a>ActivationFactoryCallback - функция
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline HRESULT STDAPICALLTYPE ActivationFactoryCallback(  
   HSTRING activationId,  
   IActivationFactory **ppFactory  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `activationId`  
 Дескриптор строка, задающая имя класса среды выполнения.  
  
 `ppFactory`  
 После завершения операции фабрики активации, соответствующий параметру `activationId`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Скорее всего, ошибки HRESULT: CLASS_E_CLASSNOTAVAILABLE и E_INVALIDARG.  
  
## <a name="remarks"></a>Примечания  
 Получает фабрику активации для активации указанного идентификатора.  
  
 Среда выполнения Windows вызывает эту функцию обратного вызова, чтобы запросить объект, указанный по имени класса среды выполнения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** module.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)