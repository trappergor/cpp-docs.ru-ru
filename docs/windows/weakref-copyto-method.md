---
title: Метод WeakRef::CopyTo | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::WeakRef::CopyTo
dev_langs:
- C++
helpviewer_keywords:
- CopyTo method
ms.assetid: f83de6da-b3d4-41a6-9845-cd725ecf3b75
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 817d984e995e7ac33ba80f978a282a8c0bac3e4f
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33890639"
---
# <a name="weakrefcopyto-method"></a>Метод WeakRef::CopyTo
Присваивает указатель на интерфейс (при его наличии) указанной переменной указателя.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HRESULT CopyTo(  
   REFIID riid,  
   _Deref_out_ IInspectable** ptr  
);  
  
template<typename U>  
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