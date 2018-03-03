---
title: "Метод Implements::FillArrayWithIid | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Implements::FillArrayWithIid
dev_langs:
- C++
helpviewer_keywords:
- FillArrayWithIid method
ms.assetid: b2e62e3f-0ab9-4c70-aad7-856268544f44
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 82561056e042e95206a8fe5e04c2a246408d7923
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="implementsfillarraywithiid-method"></a>Метод Implements::FillArrayWithIid
Вставляет идентификатор интерфейса, заданный текущим параметром шаблона нулевого в качестве элемента указанного массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
__forceinline static void FillArrayWithIid(  
   unsigned long &index,  
   _In_ IID* iids  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `index`  
 Отсчитываемый от нуля индекс, который указывает начальный элемент массива для этой операции. По завершении этой операции `index` увеличивается на 1.  
  
 `iids`  
 Массив типа IID.  
  
## <a name="remarks"></a>Примечания  
 Внутренняя вспомогательная функция.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура Implements](../windows/implements-structure.md)