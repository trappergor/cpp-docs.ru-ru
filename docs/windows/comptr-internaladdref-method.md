---
title: Метод ComPtr::InternalAddRef | Документация Майкрософт
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
ms.openlocfilehash: 30cba8b29ad6100826f580dd625bc18e2b8f9e16
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641296"
---
# <a name="comptrinternaladdref-method"></a>Метод ComPtr::InternalAddRef
Увеличивает счетчик ссылок интерфейса, связанного с данным **ComPtr**.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
void InternalAddRef() const;  
```  
  
## <a name="remarks"></a>Примечания  
 Этот метод защищен.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)