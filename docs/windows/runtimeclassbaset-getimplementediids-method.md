---
title: Метод RuntimeClassBaseT::GetImplementedIIDS | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2a5c63a3b2dbbac934162f74abb8e742cc4418a7
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40018995"
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>Метод RuntimeClassBaseT::GetImplementedIIDS
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template<typename T>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *T*  
 Тип *реализует* параметра.  
  
 *Реализует*  
 Указатель на тип, указанный параметром *T*.  
  
 *iidCount*  
 Максимальное число идентификаторов интерфейса для извлечения.  
  
 *идентификаторы IID*  
 Если эта операция завершается успешно, массив идентификаторов, реализуемый типом интерфейсов *T*.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если выполнение прошло успешно; в противном случае — значение HRESULT, описывающее ошибку.  
  
## <a name="remarks"></a>Примечания  
 Извлекает массив идентификаторов, которые реализуются с помощью указанного типа интерфейсов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)