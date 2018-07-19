---
title: Метод AsyncBase::ErrorCode | Документы Microsoft
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
ms.openlocfilehash: abd3eae18d793739866b6c0dd8a1b6a994093c93
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859583"
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
 `error`  
 Расположение, в котором эта операция сохраняет текущее код ошибки.  
  
## <a name="remarks"></a>Примечания  
 Данная операция является потокобезопасной.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)