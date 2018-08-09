---
title: Пространство имен Microsoft::WRL::Wrappers::Details | Документация Майкрософт
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
ms.openlocfilehash: 3f74f8fe3e5b637869af7b03bb2eaf5e13df9550
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40020170"
---
# <a name="microsoftwrlwrappersdetails-namespace"></a>Пространство имен Microsoft::WRL::Wrappers::Details
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
namespace Microsoft::WRL::Wrappers::Details;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="classes"></a>Классы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Класс SyncLockT](../windows/synclockt-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|  
|[Класс SyncLockWithStatusT](../windows/synclockwithstatust-class.md)|Представляет тип, который может занять монопольного или общее владение ресурсом.|  
  
### <a name="methods"></a>Методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод CompareStringOrdinal](../windows/comparestringordinal-method.md)|Сравнивает два указанных `HSTRING` объектов и возвращает целое число, которое показывает их относительное положение в порядке сортировки.|  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)