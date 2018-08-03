---
title: Метод AsyncBase::FireProgress | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireProgress
dev_langs:
- C++
helpviewer_keywords:
- FireProgress method
ms.assetid: 4512bef6-0ebc-4465-9b8a-4c9dfa82084c
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: faa2e1af556f0184fa88055bcbf154eb783e24e5
ms.sourcegitcommit: 51f804005b8d921468775a0316de52ad39b77c3e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/02/2018
ms.locfileid: "39463601"
---
# <a name="asyncbasefireprogress-method"></a>Метод AsyncBase::FireProgress
Вызывает текущий обработчик событий процесса выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void FireProgress(  
   const typename ProgressTraits::Arg2Type arg  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 *arg*  
 Метод обработчика событий для запуска.  
  
## <a name="remarks"></a>Примечания  
 `ProgressTraits` является производным от [argtraitshelper-структура](../windows/argtraitshelper-structure.md).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)