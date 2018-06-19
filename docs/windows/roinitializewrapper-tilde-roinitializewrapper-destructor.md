---
title: 'RoInitializeWrapper:: ~ RoInitializeWrapper деструктор | Документы Microsoft'
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::~RoInitializeWrapper
dev_langs:
- C++
ms.assetid: afef4c1f-ffde-4cd2-8654-8de4182eb5f4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 29683e68f1f5aadcd477cdc717b03a648c5cccc7
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892004"
---
# <a name="roinitializewrapperroinitializewrapper-destructor"></a>Деструктор RoInitializeWrapper::~RoInitializeWrapper
Отменяет инициализацию среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
~RoInitializeWrapper()  
```  
  
## <a name="remarks"></a>Примечания  
 Класс RoInitializeWrapper вызывает Windows::Foundation::Uninitialize().  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)