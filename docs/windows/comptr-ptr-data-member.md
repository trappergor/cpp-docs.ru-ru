---
title: "Элемент данных Comptr::ptr_ | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ptr_
dev_langs: C++
helpviewer_keywords: ptr_ data member
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5449489964108fdd6221779583661238f87d82ea
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="comptrptr-data-member"></a>Элемент данных ComPtr::ptr_
Содержит указатель на интерфейс, который связан с данным объектом ComPtr и управляется им.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType *ptr_;  
```  
  
## <a name="remarks"></a>Примечания  
 `ptr_`является членом внутреннего, защищенных данных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)