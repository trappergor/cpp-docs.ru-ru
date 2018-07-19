---
title: Метод EventTargetArray::AddTail | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::AddTail
dev_langs:
- C++
helpviewer_keywords:
- AddTail method
ms.assetid: d0fafab9-049c-40e0-a40c-d126c9ee63e6
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 0bc56e13c8d07841ceb1f341228d7a963fda2dd8
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872287"
---
# <a name="eventtargetarrayaddtail-method"></a>Метод EventTargetArray::AddTail
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `element`  
 Указатель на обработчик событий для добавления.  
  
## <a name="remarks"></a>Примечания  
 Добавляет указанный обработчик события в конец массива внутренних обработчиков событий.  
  
 AddTail() предназначен для внутреннего использования только класса EventSource.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Eventtargetarray-класс](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)