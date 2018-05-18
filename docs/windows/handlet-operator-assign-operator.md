---
title: HandleT::operator =-оператор | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::operator=
dev_langs:
- C++
helpviewer_keywords:
- operator= operator
ms.assetid: 9e42dcca-30fa-4e8b-8954-802fd64a5595
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 6a13e8eb7e74625e185b59816b5794b0390e95e3
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="handletoperator-operator"></a>Оператор HandleT::operator=
Перемещение текущего объекта HandleT значение указанного объекта HandleT.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
HandleT& operator=(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `h`  
 Ссылка rvalue на дескриптор.  
  
## <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект HandleT.  
  
## <a name="remarks"></a>Примечания  
 Эта операция делает недействительными объекта HandleT, заданного параметром `h`.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)