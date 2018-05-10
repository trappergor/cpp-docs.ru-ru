---
title: Элемент данных Comptr::ptr_ | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::ptr_
dev_langs:
- C++
helpviewer_keywords:
- ptr_ data member
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d995c8e35ed35d4581d8eec8b74fda1ebbca6519
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptrptr-data-member"></a>Элемент данных ComPtr::ptr_
Содержит указатель на интерфейс, который связан с данным объектом ComPtr и управляется им.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
InterfaceType *ptr_;  
```  
  
## <a name="remarks"></a>Примечания  
 `ptr_` является членом внутреннего, защищенных данных.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)