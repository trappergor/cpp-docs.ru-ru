---
title: Класс EventTargetArray | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::EventTargetArray
dev_langs:
- C++
helpviewer_keywords:
- EventTargetArray class
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4461004a1681d9095449c51fb9cb3973d5017693
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33881313"
---
# <a name="eventtargetarray-class"></a>Класс EventTargetArray
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет массив дескрипторов событий.  
  
 Обработчики событий, связанных с [EventSource](../windows/eventsource-class.md) объекта хранятся в защищенный элемент данных EventTargetArray.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор EventTargetArray::EventTargetArray](../windows/eventtargetarray-eventtargetarray-constructor.md)|Инициализирует новый экземпляр класса EventTargetArray.|  
|[Деструктор EventTargetArray::~EventTargetArray](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Деинициализирует текущий класс EventTargetArray.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод EventTargetArray::AddTail](../windows/eventtargetarray-addtail-method.md)|Добавляет указанный обработчик события в конец массива внутренних обработчиков событий.|  
|[Метод EventTargetArray::Begin](../windows/eventtargetarray-begin-method.md)|Получает адрес первого элемента во внутреннем массиве обработчиков событий.|  
|[Метод EventTargetArray::End](../windows/eventtargetarray-end-method.md)|Возвращает адрес последнего элемента в массиве внутреннего обработчиков событий.|  
|[Метод EventTargetArray::Length](../windows/eventtargetarray-length-method.md)|Возвращает текущее количество элементов в массиве внутреннего обработчиков событий.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EventTargetArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)