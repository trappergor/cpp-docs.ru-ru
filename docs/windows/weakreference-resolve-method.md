---
title: "Метод WeakReference::Resolve | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::Resolve
dev_langs:
- C++
helpviewer_keywords:
- Resolve method
ms.assetid: fc65a4b7-48a0-4d64-a793-37f566fdd8e7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4da4689ffd8fa0a633b3f481b0292d060e57345
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="weakreferenceresolve-method"></a>Метод WeakReference::Resolve
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
  
STDMETHOD(Resolve)  
   (REFIID riid,   
   _Deref_out_opt_ IInspectable **ppvObject  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `ppvObject`  
 После завершения операции копию текущей строгую ссылку, если число строгая ссылка имеет ненулевое значение.  
  
## <a name="return-value"></a>Возвращаемое значение  
  
-   Значение S_OK, если операция завершилась успешно, и строгой ссылки счетчика равно нулю. Значение параметра `ppvObject` — `nullptr`.  
  
-   Значение S_OK, если операция завершилась успешно и количество строгая ссылка имеет ненулевое значение. `ppvObject` Параметра равным строгую ссылку.  
  
-   В противном случае — значение HRESULT, указывающее причину неудачного завершения операции.  
  
## <a name="remarks"></a>Примечания  
 Устанавливает заданный указатель текущее значение строгую ссылку, если число строгая ссылка имеет ненулевое значение.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Класс WeakReference 1](../windows/weakreference-class1.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)