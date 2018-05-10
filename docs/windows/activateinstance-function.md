---
title: Функция ActivateInstance | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Windows::Foundation::ActivateInstance
- client/ABI::Windows::Foundation::ActivateInstance
dev_langs:
- C++
helpviewer_keywords:
- ActivateInstance function
ms.assetid: 8cfd1dd9-5fda-4cc2-acf8-d40e783b3875
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c0bf945dd8225ca3c153d7f497ded6b83ebd022d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
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
  
 **Пространство имен:** Windows::Foundation  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)