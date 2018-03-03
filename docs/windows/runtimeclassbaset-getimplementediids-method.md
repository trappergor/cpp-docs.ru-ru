---
title: "Метод RuntimeClassBaseT::GetImplementedIIDS | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::GetImplementedIIDS
dev_langs:
- C++
helpviewer_keywords:
- GetImplementedIIDS method
ms.assetid: adae54da-521d-4add-87f5-242fbd85f33b
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 25410ac57e1812d3f4648151afff4f97d413689b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassbasetgetimplementediids-method"></a>Метод RuntimeClassBaseT::GetImplementedIIDS
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
__forceinline static HRESULT GetImplementedIIDS(  
   _In_ T* implements,  
   _Out_ ULONG *iidCount,  
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип параметра `implements`.  
  
 `implements`  
 Указатель на тип, указанный параметром `T`.  
  
 `iidCount`  
 Максимальное количество идентификаторов интерфейса для извлечения.  
  
 `iids`  
 Если эта операция завершается успешно, массив идентификаторов, реализуемый типом интерфейса `T`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение HRESULT, описывающее ошибку.  
  
## <a name="remarks"></a>Примечания  
 Извлекает массив идентификаторов, которые реализуются указанного типа интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)