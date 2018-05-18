---
title: Пространство имен Microsoft::WRL::Wrappers::Details | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details
- internal/Microsoft::WRL::Details
- async/Microsoft::WRL::Details
- corewrappers/Microsoft::WRL::Wrappers::Details
- client/Microsoft::WRL::Details
- module/Microsoft::WRL::Details
- event/Microsoft::WRL::Details
dev_langs:
- C++
helpviewer_keywords:
- Details namespace
ms.assetid: 6d3f04ac-9b53-4a82-a188-a85309ec34a4
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 752989b33bd0b017233ea4a105d2ad36ca2290f4
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::Details
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
namespace Microsoft::WRL::Wrappers::Details;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Класс SyncLockT](../windows/synclockt-class.md)|Представляет тип, который может принимать монопольного или общие права владения ресурсом.|  
|[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)|Представляет тип, который может принимать монопольного или общие права владения ресурсом.|  
  
### <a name="methods"></a>Методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод CompareStringOrdinal](../windows/comparestringordinal-method.md)|Сравнивает два указанных `HSTRING` объектов и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)