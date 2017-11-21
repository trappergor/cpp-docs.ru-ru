---
title: "Метод AsyncBase::OnCancel | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::OnCancel
dev_langs: C++
helpviewer_keywords: OnCancel method
ms.assetid: 4bd0b68e-a9df-4913-9f6c-e093ed55c3f9
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e46f673329697ef503dafcc6a3b683fa2224525a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="asyncbaseoncancel-method"></a>Метод AsyncBase::OnCancel
При переопределении в производном классе отменяет асинхронную операцию.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual void OnCancel(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)   
 [Метод AsyncBase::Cancel](../windows/asyncbase-cancel-method.md)