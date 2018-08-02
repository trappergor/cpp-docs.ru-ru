---
title: Метод AsyncBase::Close | Документация Майкрософт
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
ms.openlocfilehash: 9d0798a6ef593e388ce7867ee9a55763be9ae890
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463363"
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
 Значение S_OK, если операция закрывает или уже закрыт; в противном случае E_ILLEGAL_STATE_CHANGE.  
  
## <a name="remarks"></a>Примечания  
 **Метод Close()** — это реализация по умолчанию `IAsyncInfo::Close`, а не фактические работает. Чтобы действительно закрыть асинхронную операцию, переопределите `OnClose()` чисто виртуального метода.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)