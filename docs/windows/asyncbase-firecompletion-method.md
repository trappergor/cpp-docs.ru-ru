---
title: Метод AsyncBase::FireCompletion | Документы Microsoft
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
ms.openlocfilehash: 0cd18d340a11575ed9f6f52d92a5910dcee1faec
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33859739"
---
# <a name="asyncbasefirecompletion-method"></a>Метод AsyncBase::FireCompletion
Вызывается обработчик события завершения или сбрасывает делегат внутренней хода выполнения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Примечания  
 Первая версия FireCompletion() сбрасывает переменной делегата внутренней хода выполнения. Вторая версия вызывает обработчик событий завершения при завершении асинхронной операции.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)