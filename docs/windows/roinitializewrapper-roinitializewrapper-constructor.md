---
title: Конструктор RoInitializeWrapper::RoInitializeWrapper | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::RoInitializeWrapper::RoInitializeWrapper
dev_langs:
- C++
ms.assetid: c6f7fb07-14af-4574-9135-cea164607f30
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64f2af40c671760bb8d4e667c209598c46b24665
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33889213"
---
# <a name="roinitializewrapperroinitializewrapper-constructor"></a>Конструктор RoInitializeWrapper::RoInitializeWrapper
Инициализирует новый экземпляр класса RoInitializeWrapper.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
RoInitializeWrapper(   RO_INIT_TYPE flags)  
```  
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 Одно из перечислений RO_INIT_TYPE, которые задает поддержку, предоставляемые средой выполнения Windows.  
  
## <a name="remarks"></a>Примечания  
 Класс RoInitializeWrapper вызывает Windows::Foundation::Initialize (*флаги*).  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)