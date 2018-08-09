---
title: Конструктор Semaphore::Semaphore | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Semaphore::Semaphore
dev_langs:
- C++
helpviewer_keywords:
- Semaphore, constructor
ms.assetid: 91c22ae7-181e-460d-ad40-70c3a53b26fd
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 3646e13818297b636a888e1ad00c998a120e8379
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39643664"
---
# <a name="semaphoresemaphore-constructor"></a>Конструктор Semaphore::Semaphore
Инициализирует новый экземпляр класса **семафора** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit Semaphore(  
   HANDLE h  
);  
  
WRL_NOTHROW Semaphore(  
   _Inout_ Semaphore&& h  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор или rvalue ссылка для **семафора** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Semaphore](../windows/semaphore-class.md)