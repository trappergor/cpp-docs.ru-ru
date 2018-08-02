---
title: Метод AsyncBase::ErrorCode | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::ErrorCode
dev_langs:
- C++
helpviewer_keywords:
- ErrorCode method
ms.assetid: 3f5f0f69-d60a-4a67-8cc6-a55fdc89a192
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 580df181e544ced6594b049b85d7f147bd2fe22e
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39464620"
---
# <a name="asyncbaseerrorcode-method"></a>Метод AsyncBase::ErrorCode
Получает код ошибки для текущей асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
inline void ErrorCode(  
   HRESULT *error  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *Ошибка*  
 Расположение, в котором эта операция сохраняет текущий код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Данная операция является потокобезопасной.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)