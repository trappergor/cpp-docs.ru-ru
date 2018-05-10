---
title: Метод HandleT::Detach | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- corewrappers/Microsoft::WRL::Wrappers::HandleT::Detach
dev_langs:
- C++
helpviewer_keywords:
- Detach method
ms.assetid: f7df0f90-fafb-4d1b-a215-a6c62941f6b0
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 100d215099494c9b2714fd2c42dee69644a5006c
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="handletdetach-method"></a>Метод HandleT::Detach
Отсоединяет текущий объект HandleT из его базового дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
typename HandleTraits::Type Detach();  
```  
  
## <a name="return-value"></a>Возвращаемое значение  
 Базовый дескриптор.  
  
## <a name="remarks"></a>Примечания  
 По завершении этой операции текущего объекта HandleT присваивается недопустимое состояние.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Класс HandleT](../windows/handlet-class.md)