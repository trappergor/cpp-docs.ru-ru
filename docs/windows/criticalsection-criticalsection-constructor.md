---
title: Конструктор CriticalSection::CriticalSection | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::CriticalSection::CriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CriticalSection, constructor
ms.assetid: 930b89be-4d74-46bd-8879-5dd4d15bcbd0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: f87f95a0683f6b4440d2be8b770902a7e4ecde59
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39644298"
---
# <a name="criticalsectioncriticalsection-constructor"></a>Конструктор CriticalSection::CriticalSection
Инициализирует объект синхронизации, аналогичны объект mutex, но может использоваться только потоки одного процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *spinCount*  
 Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о критических секциях и прокруток см. в разделе `InitializeCriticalSectionAndSpinCount` работать в **синхронизации** раздел документации по Windows API.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс CriticalSection](../windows/criticalsection-class.md)