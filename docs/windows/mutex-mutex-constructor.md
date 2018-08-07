---
title: Конструктор Mutex::Mutex | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Mutex::Mutex
dev_langs:
- C++
helpviewer_keywords:
- Mutex, constructor
ms.assetid: 504afcdc-775a-4c98-a06f-4fb4663eba3f
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 7a7549371ba4648f8fcce03a98a021c8027c676e
ms.sourcegitcommit: 4586bfc32d8bc37ab08b24816d7fad5df709bfa3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/07/2018
ms.locfileid: "39605198"
---
# <a name="mutexmutex-constructor"></a>Конструктор Mutex::Mutex
Инициализирует новый экземпляр класса **мьютекс** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
explicit Mutex(  
   HANDLE h  
);  
  
Mutex(  
   _Inout_ Mutex&& h  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор или rvalue ссылка на дескриптор для **мьютекс** объекта.  
  
## <a name="remarks"></a>Примечания  
 Первый конструктор инициализирует **мьютекс** объект из указанного дескриптора. Второй конструктор инициализирует **мьютекс** объект из указанного дескриптора, а затем перемещает владение мьютексом текущему **мьютекс** объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers
 
 ## <a name="see-also"></a>См. также
 [Класс Mutex](../windows/mutex-class1.md)