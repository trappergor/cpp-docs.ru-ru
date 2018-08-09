---
title: Activateinstance-функция | Документация Майкрософт
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
ms.openlocfilehash: 93b1c8fa12e06984a2bffdd90419c481d8897b94
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646245"
---
# <a name="activateinstance-function"></a>ActivateInstance - функция
Регистрирует и возвращает экземпляр заданного типа, определенного в идентификатор указанного класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T>  
inline HRESULT ActivateInstance(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> instance  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Типа, подлежащего активации.  
  
 *activatableClassId*  
 Имя идентификатора класса, определяет параметр *T*.  
  
 *экземпляр*  
 После завершения операции, ссылку на экземпляр *T*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае ошибку HRESULT, которые указывают на причину ошибки.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Windows::Foundation  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Windows::Foundation](../windows/windows-foundation-namespace.md)