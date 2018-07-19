---
title: Метод ImplementsHelper::CanCastTo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::ImplementsHelper::CanCastTo
dev_langs:
- C++
helpviewer_keywords:
- CanCastTo method
ms.assetid: 9ae6fa17-d0b1-4e31-9ae5-da6ae4026e32
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6de971f2de2421a2d7987dab30ba73fa2d225b15
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33876557"
---
# <a name="implementshelpercancastto-method"></a>Метод ImplementsHelper::CanCastTo
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
HRESULT CanCastTo(  
   REFIID riid,  
   _Deref_out_ void **ppv  
);  
  
HRESULT CanCastTo(  
   _In_ const IID &iid,  
   _Deref_out_ void **ppv  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Ссылка на идентификатор интерфейса.  
  
 `ppv`  
 Если операция завершилась успешно, указатель на интерфейс, заданный `riid` или `iid`.  
  
 `iid`  
 Ссылка на идентификатор интерфейса.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="remarks"></a>Примечания  
 Возвращает указатель на идентификатор указанного интерфейса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Implementshelper-структура](../windows/implementshelper-structure.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)