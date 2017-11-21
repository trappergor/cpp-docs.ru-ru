---
title: "Конструктор Mutex::Mutex | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs: C++
helpviewer_keywords: Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d2a0187c26f8f0a170881d0b683cb462a0a24b81
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mutexmutex-constructor"></a>Конструктор Mutex::Mutex
Инициализирует новый экземпляр класса Mutex.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор или rvalue-ссылка на дескриптор объекта Mutex.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует объект Mutex из указанного дескриптора. Второй конструктор инициализирует объект Mutex из указанного дескриптора, а затем передает право на владение мьютексом на текущий объект Mutex.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Mutex](../windows/mutex-class1.md)