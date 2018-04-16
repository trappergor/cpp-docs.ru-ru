---
title: Метод RuntimeClassBaseT::AsIID | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 17d67ee58e9ecc3b0ef463d6af132fec3a1c0a2f
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/22/2018
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
  
 **Namespace:** Microsoft::WRL::Details  
  
## <a name="see-also"></a>См. также  
 [Структура RuntimeClassBaseT](../windows/runtimeclassbaset-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)