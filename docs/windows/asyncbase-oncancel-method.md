---
title: Метод AsyncBase::OnCancel | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs:
- C++
helpviewer_keywords:
- OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b648718c715a43befbc5ead828c810dbfa92d120
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39646878"
---
# <a name="asyncbaseoncancel-method"></a>Метод AsyncBase::OnCancel
При переопределении в производном классе отменяет асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Asyncbase-класс](../windows/asyncbase-class.md)   
 [Метод AsyncBase::Cancel](../windows/asyncbase-cancel-method.md)