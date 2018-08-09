---
title: Класс EventTargetArray | Документация Майкрософт
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
ms.openlocfilehash: 4cf5f885a002ede8a715eb4850eef5a8810a0309
ms.sourcegitcommit: 37a10996022d738135999cbe71858379386bab3d
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/08/2018
ms.locfileid: "39648364"
---
# <a name="eventtargetarray-class"></a>Класс EventTargetArray
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет собой массив обработчики событий.  
  
 Обработчики событий, связанных с [EventSource](../windows/eventsource-class.md) объекта хранятся в защищенный **EventTargetArray** данные-член.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор EventTargetArray::EventTargetArray](../windows/eventtargetarray-eventtargetarray-constructor.md)|Инициализирует новый экземпляр класса **EventTargetArray** класса.|  
|[Деструктор EventTargetArray::~EventTargetArray](../windows/eventtargetarray-tilde-eventtargetarray-destructor.md)|Деинициализирует текущий **EventTargetArray** класса.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод EventTargetArray::AddTail](../windows/eventtargetarray-addtail-method.md)|Добавляет указанный обработчик событий в конец внутреннего массива из обработчиков событий.|  
|[Метод EventTargetArray::Begin](../windows/eventtargetarray-begin-method.md)|Получает адрес первого элемента во внутреннем массиве обработчиков событий.|  
|[Метод EventTargetArray::End](../windows/eventtargetarray-end-method.md)|Возвращает адрес последнего элемента в массиве внутренних обработчиков событий.|  
|[Метод EventTargetArray::Length](../windows/eventtargetarray-length-method.md)|Получает текущее число элементов в массиве внутренних обработчиков событий.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EventTargetArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)