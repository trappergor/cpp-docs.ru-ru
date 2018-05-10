---
title: Метод AsyncBase::Close | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4f3f36656b9316fb6ad980349a836fad31c3a9a0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="asyncbaseclose-method"></a>Метод AsyncBase::Close
Закрывает асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
STDMETHOD(  
   Close  
)(void) override;  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Значение S_OK, если операция закрывается или уже закрыт; в противном случае E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Примечания  
 Close() IAsyncInfo::Close это реализация по умолчанию, а не фактический работает. Действительно закрыть асинхронную операцию, переопределите OnClose() чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)