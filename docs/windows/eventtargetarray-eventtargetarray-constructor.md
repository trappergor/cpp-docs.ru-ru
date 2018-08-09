---
title: Конструктор EventTargetArray::EventTargetArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray, constructor
ms.assetid: 6c6d3737-3cd3-4515-a8f6-d27901bb8ed2
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 59753f592f099f80396f408fa531756ba91b308e
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39652543"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>Конструктор EventTargetArray::EventTargetArray
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
### <a name="parameters"></a>Параметры  
 *hr*  
 После этого конструктор операций параметр *hr* указывает, успешно ли выполнено выделения массива. В следующей таблице перечислены возможные значения для *hr*.  
  
 S_OK  
 Операция успешно выполнена.  
  
 E_OUTOFMEMORY  
 Не удалось выделить память для массива.  
  
 S_FALSE  
 Параметр *элементы* меньше или равно нулю.  
  
 *Элементы*  
 Число элементов массива для выделения.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса **EventTargetArray** класса.  
  
 **EventTargetArray** используется для сохранения массив дескрипторов событий в `EventSource` объекта.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Класс EventTargetArray](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)