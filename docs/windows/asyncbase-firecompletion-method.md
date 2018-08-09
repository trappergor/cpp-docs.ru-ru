---
title: Метод AsyncBase::FireCompletion | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs:
- C++
helpviewer_keywords:
- FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 199d84afe198c4fc41808144105ea704822aa00a
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646611"
---
# <a name="asyncbasefirecompletion-method"></a>Метод AsyncBase::FireCompletion
Вызывает обработчик события завершения или сбрасывает делегат внутренней хода выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Примечания  
 Первая версия **FireCompletion()** сбрасывает переменной делегата внутренней хода выполнения. Вторая версия вызывает обработчик события завершения, если асинхронная операция завершена.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)