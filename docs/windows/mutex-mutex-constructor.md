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
ms.openlocfilehash: d87c07f7fa4f1dfa6cbb34545d74d75e8a867583
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017088"
---
# <a name="mutexmutex-constructor"></a>Конструктор Mutex::Mutex
Инициализирует новый экземпляр класса **мьютекс** класса.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
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