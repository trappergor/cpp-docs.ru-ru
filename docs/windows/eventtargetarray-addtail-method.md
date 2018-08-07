---
title: Метод EventTargetArray::AddTail | Документация Майкрософт
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
ms.openlocfilehash: b469adedebda2beb64c531c82d10f90cc4114742
ms.sourcegitcommit: d5d6bb9945c3550b8e8864b22b3a565de3691fde
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/06/2018
ms.locfileid: "39570178"
---
# <a name="eventtargetarrayaddtail-method"></a>Метод EventTargetArray::AddTail
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
void AddTail(  
   _In_ IUnknown* element  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *Элемент*  
 Указатель на обработчик событий для добавления.  
  
## <a name="remarks"></a>Примечания  
 Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.  
  
 **AddTail()** предназначен для использования в среде только `EventSource` класса.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Класс EventTargetArray](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)