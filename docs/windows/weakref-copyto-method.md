---
title: "Метод WeakRef::CopyTo | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 5b0114a9768fbea12a5b98f51911267cb24b0b43
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="weakrefcopyto-method"></a>Метод WeakRef::CopyTo
Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<  
   typename U  
>  
HRESULT CopyTo(  
   _Deref_out_ U** ptr  
);  
  
HRESULT CopyTo(  
   _Deref_out_ IWeakReference** ptr  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `U`  
 Указатель на интерфейс IInspectable. Если параметр `U` не получен из IInspectable, возникает ошибка.  
  
 `riid`  
 Идентификатор интерфейса. Если параметр `riid` не получен из **IWeakReference**, возникает ошибка.  
  
 `ptr`  
 Двойной косвенный указатель на IInspectable или IWeakReference.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, описывающее тип сбоя. Дополнительные сведения см. в разделе "Замечания".  
  
## <a name="remarks"></a>Примечания  
 Возвращаемое значение S_OK означает, что эта операция завершилась успешно, но не указывает, была ли слабая ссылка разрешена в строгую ссылку. Если возвращается значение S_OK, проверьте, содержит ли параметр `p` строгую ссылку, то есть не имеет ли параметр `p` значение `nullptr`.  
  
 Начиная с пакета SDK для Windows 10 этот метод не устанавливает экземпляр WeakRef в значение `nullptr` , если не удалось получить слабую ссылку, поэтому следует избегать использования кода проверки ошибок, который проверяет наличие `nullptr`для WeakRef. Вместо этого проверьте `ptr` для `nullptr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс WeakRef](../windows/weakref-class.md)