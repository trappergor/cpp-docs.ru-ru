---
title: "Метод AsyncBase::Close | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::Close
dev_langs: C++
helpviewer_keywords: Close method
ms.assetid: a52b1124-754b-4393-b491-64aae0c22f1c
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dbdc52eec476b973c3d3549cfb0ff9413a46f6f3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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