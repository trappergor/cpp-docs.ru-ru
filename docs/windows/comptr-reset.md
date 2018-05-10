---
title: ComPtr::Reset | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
dev_langs:
- C++
ms.assetid: aa6a46f7-f56b-4fd5-add0-7cea55f7abda
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd2ce820367b15cb5dad8baf691a835499457a55
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="comptrreset"></a>ComPtr::Reset
Освобождает все ссылки на указатель на интерфейс, который связан с данным объектом ComPtr.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
unsigned long Reset();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Число освобожденных ссылок, если таковые имеются.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** client.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Класс ComPtr](../windows/comptr-class.md)