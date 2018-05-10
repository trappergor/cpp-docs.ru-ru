---
title: Метод ComPtr::InternalAddRef | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::InternalAddRef
dev_langs:
- C++
helpviewer_keywords:
- InternalAddRef method
ms.assetid: f8e860ef-c56e-42a6-a712-77aaab1464ab
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 55f2ffc540ba6680636b85e73b7b4fbe96068ab3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptrinternaladdref-method"></a>Метод ComPtr::InternalAddRef
Увеличивает счетчик ссылок интерфейса, связанного с этим объектом ComPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void InternalAddRef() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Этот метод защищен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)