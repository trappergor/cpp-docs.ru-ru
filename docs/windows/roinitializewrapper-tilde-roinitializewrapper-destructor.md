---
title: 'RoInitializeWrapper:: ~ RoInitializeWrapper деструктор | Документация Майкрософт'
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
ms.openlocfilehash: 1c6eaeb044cf3e169bf5927a2fec948cc8d4294c
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39606280"
---
# <a name="roinitializewrapperroinitializewrapper-destructor"></a>Деструктор RoInitializeWrapper::~RoInitializeWrapper
Отменяет инициализацию среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
~RoInitializeWrapper()  
```  
  
## <a name="remarks"></a>Примечания  
 **RoInitializeWrapper** класс вызывает `Windows::Foundation::Uninitialize()`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)