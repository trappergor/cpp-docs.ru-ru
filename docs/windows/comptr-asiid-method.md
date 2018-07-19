---
title: Метод ComPtr::AsIID | Документация Майкрософт
ms.custom: ''
ms.date: 07/11/2018
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::AsIID
dev_langs:
- C++
helpviewer_keywords:
- AsIID method
ms.assetid: d5a3cdb2-796d-4410-966a-847c0e8fb226
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: db5bc6b2547fb77dd887f96b6c33dee536e43f77
ms.sourcegitcommit: 76fd30ff3e0352e2206460503b61f45897e60e4f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/13/2018
ms.locfileid: "39025907"
---
# <a name="comptrasiid-method"></a>Метод ComPtr::AsIID
Возвращает объект ComPtr, представляющий интерфейс, определенный указанным идентификатором интерфейса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW HRESULT AsIID(  
   REFIID riid,  
   _Out_ ComPtr<IUnknown>* p  
) const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `riid`  
 Идентификатор интерфейса.  
  
 `p`  
 Если объект имеет интерфейс, идентификатор которой равняется `riid`, двойной косвенный указатель на интерфейс, определенный следующим `riid` параметра; в противном случае указатель на интерфейс IUnknown.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция завершилась успешно; в противном случае — значение HRESULT, указывающее на ошибку.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)