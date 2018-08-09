---
title: Конструктор HandleT::HandleT | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs:
- C++
helpviewer_keywords:
- HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a0bb864fa1356089552fb3c48461fef2a63920b
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39641383"
---
# <a name="handlethandlet-constructor"></a>Конструктор HandleT::HandleT
Инициализирует новый экземпляр класса **HandleT** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует **HandleT** объект, который не является допустимым дескриптором для объекта. Второй конструктор создает новый **HandleT** объект из параметра *h*.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)