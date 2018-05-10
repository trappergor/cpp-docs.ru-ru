---
title: Конструктор CriticalSection::CriticalSection | Документы Microsoft
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
ms.openlocfilehash: d86c80d169cb6d9794f163290c30bf1b2563588b
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="criticalsectioncriticalsection-constructor"></a>Конструктор CriticalSection::CriticalSection
Инициализирует объект синхронизации, который похож на объекте mutex, но может использоваться только потоками одного процесса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit CriticalSection(  
   ULONG spincount = 0  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `spincount`  
 Счетчик прокруток для объекта критической секции. Значение по умолчанию — 0.  
  
## <a name="remarks"></a>Примечания  
 Дополнительные сведения о критических секциях и счетчике прокруток см. в разделе **InitializeCriticalSectionAndSpinCount** функции в разделе синхронизация документации по Windows API.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс CriticalSection](../windows/criticalsection-class.md)
