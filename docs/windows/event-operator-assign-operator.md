---
title: Event::operator =-оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::Event::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: d8fe9820-8856-4899-9553-56226bdc4945
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d3da41ff7fd145889ec799bb2f8ebe99aed36934
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="eventoperator-operator"></a>Оператор Event::operator=
Присваивает указанную ссылку на событие текущему экземпляру Event.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW Event& operator=(  
   _Inout_ Event&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Rvalue ссылка на экземпляр события.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Указатель на текущий экземпляр события.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-class-windows-runtime-cpp-template-library.md)