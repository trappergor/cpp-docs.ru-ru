---
title: "Класс EventTargetArray | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "event/Microsoft::WRL::Details::EventTargetArray"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "EventTargetArray - класс"
ms.assetid: e3cadb7c-2160-4cbb-a2f8-c28733d1e96d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс EventTargetArray
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Поддерживает инфраструктуру WRL и не предназначен для непосредственного использования в коде.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class EventTargetArray : public Microsoft::WRL::RuntimeClass<Microsoft::WRL::RuntimeClassFlags<ClassicCom>, IUnknown>;  
```  
  
## <a name="remarks"></a>Примечания  
 Представляет массив обработчики событий.  
  
 Обработчики событий, связанных с [EventSource](../windows/eventsource-class.md) объекта хранятся в защищенный член данных EventTargetArray.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор EventTargetArray::EventTargetArray](../windows/eventtargetarray-eventtargetarray-constructor.md)|Инициализирует новый экземпляр класса EventTargetArray.|  
|[EventTargetArray:: ~ EventTargetArray деструктор](../Topic/EventTargetArray::~EventTargetArray%20Destructor.md)|Деинициализирует текущий класс EventTargetArray.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод EventTargetArray::AddTail](../windows/eventtargetarray-addtail-method.md)|Добавляет указанный обработчик событий в конец внутреннего массива обработчиками событий.|  
|[Метод EventTargetArray::Begin](../windows/eventtargetarray-begin-method.md)|Получает адрес первого элемента в массиве внутреннего обработчиков событий.|  
|[Метод EventTargetArray::End](../windows/eventtargetarray-end-method.md)|Возвращает адрес последнего элемента в массиве внутреннего обработчиков событий.|  
|[Метод EventTargetArray::Length](../windows/eventtargetarray-length-method.md)|Возвращает текущее количество элементов в массиве внутреннего обработчиков событий.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `EventTargetArray`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)