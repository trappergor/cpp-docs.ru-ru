---
title: Конструктор EventTargetArray::EventTargetArray | Документы Microsoft
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
ms.openlocfilehash: fbfd12ea513044f1062e60f5c73f5089683f043d
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33872719"
---
# <a name="eventtargetarrayeventtargetarray-constructor"></a>Конструктор EventTargetArray::EventTargetArray
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
EventTargetArray(  
   _Out_ HRESULT* hr,  
   size_t items  
);  
```  
  
#### <a name="parameters"></a>Параметры  
 `hr`  
 После этого конструктор операций параметр `hr` указывает, успешно ли выполнено выделение массива. В следующей таблице перечислены возможные значения для `hr`.  
  
 S_OK  
 Операция успешно выполнена.  
  
 E_OUTOFMEMORY  
 Не удалось выделить память для массива.  
  
 S_FALSE  
 Параметр `items` меньше или равно нулю.  
  
 `items`  
 Число элементов массива для выделения.  
  
## <a name="remarks"></a>Примечания  
 Инициализирует новый экземпляр класса EventTargetArray.  
  
 EventTargetArray используется для хранения массива из обработчиков событий в объекта EventSource.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Eventtargetarray-класс](../windows/eventtargetarray-class.md)   
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)