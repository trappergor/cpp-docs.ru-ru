---
title: Метод RuntimeClassBaseT::AsIID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 35d218666f785685e95d737574ff44e276ce84b3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892134"
---
# <a name="runtimeclassbasetasiid-method"></a>Метод RuntimeClassBaseT::AsIID
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<typename T>  
__forceinline static HRESULT AsIID(  
   _In_ T* implements,  
   REFIID riid,  
   _Deref_out_ void **ppvObject  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип, который реализует идентификатор интерфейса, заданный параметром `riid`.  
  
 `implements`  
 Переменная типа, указанного в параметре шаблона `T`.  
  
 `riid`  
 Извлекаемый идентификатор интерфейса.  
  
 `ppvObject`  
 Если операция завершилась успешно, представляет указатель на указатель интерфейса, заданный параметром `riid`.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если успешно; в противном случае — значение HRESULT, описывающее ошибку.  
  
## <a name="remarks"></a>Примечания  
 Извлекает указатель на идентификатор указанного интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)