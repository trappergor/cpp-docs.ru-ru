---
title: "Метод RuntimeClassBaseT::AsIID | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::RuntimeClassBaseT::AsIID
dev_langs: C++
helpviewer_keywords: AsIID method
ms.assetid: 90d7df8a-cf9e-4eef-8837-bc1a25f3fa1a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 482edbcabf368f68a720910717650be78ac11c62
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassbasetasiid-method"></a>Метод RuntimeClassBaseT::AsIID
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
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