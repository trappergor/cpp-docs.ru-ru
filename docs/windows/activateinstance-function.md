---
title: Функция ActivateInstance | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4ccf4195ac81188520ced79581c131c564cfbb9
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
---
# <a name="activateinstance-function"></a>ActivateInstance - функция
Регистрирует и извлекает экземпляр заданного типа, определенного в идентификатор указанного класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип для активации.  
  
 `activatableClassId`  
 Имя идентификатора класса, которая определяет параметр `T`.  
  
 `instance`  
 После завершения операции, ссылку на экземпляр `T`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение HRESULT, указывающее причину ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)