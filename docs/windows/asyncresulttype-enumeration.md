---
title: Перечисление AsyncResultType | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncResultType
dev_langs:
- C++
helpviewer_keywords:
- AsyncResultType enumeration
ms.assetid: 4195d234-3f3f-4363-9118-6ad2a7551cf2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8171c4a57621a4f17a5f0ddb0745faa70fde6524
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39465289"
---
# <a name="asyncresulttype-enumeration"></a>AsyncResultType - перечисление
Указывает тип результата, возвращенный `GetResults()` метод.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
enum AsyncResultType;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="values"></a>Значения  
  
|Имя|Описание:|  
|----------|-----------------|  
|`MultipleResults`|Набор нескольких результатов, которые представлены постепенно между `Start` состояние и перед `Close()` вызывается.|  
|`SingleResult`|Один результат, который представлен после завершения события.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)