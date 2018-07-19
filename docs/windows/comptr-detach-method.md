---
title: Метод ComPtr::Detach | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::ComPtr::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: b9016775-1ade-4581-be1f-0d6f9c2ca658
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: afa5976d26351ed3022c58fa8226b6038fa816c0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33883597"
---
# <a name="comptrdetach-method"></a>Метод ComPtr::Detach
Отменяет связь этого объекта `ComPtr` с интерфейсом, который он представляет.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
T* Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на интерфейс, который был представлен этим объектом `ComPtr`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)