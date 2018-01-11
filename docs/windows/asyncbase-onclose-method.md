---
title: "Метод AsyncBase::OnClose | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::OnClose
dev_langs: C++
helpviewer_keywords: OnClose method
ms.assetid: 96766450-c262-4611-8534-7d190b799142
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f0a15a8c7089e6d24171ae552008c2b7c8ccafcd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbaseonclose-method"></a>Метод AsyncBase::OnClose
При переопределении в производном классе, закрывает асинхронной операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
virtual void OnClose(  
   void  
) = 0;  
```  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** async.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс AsyncBase](../windows/asyncbase-class.md)   
 [Метод AsyncBase::Close](../windows/asyncbase-close-method.md)