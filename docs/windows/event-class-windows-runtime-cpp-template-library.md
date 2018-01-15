---
title: "Класс событий (библиотека шаблонов C++ среды выполнения Windows) | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Event
dev_langs: C++
ms.assetid: 55dfc9fc-62d4-4bb2-9d85-5b6dd88569e8
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4647a8b1001cd6acd6b70a3d15f127c8e3891c1c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="event-class-windows-runtime-c-template-library"></a>Класс Event (библиотека шаблонов C++ среды выполнения Windows)
Представляет событие.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class Event : public HandleT<HandleTraits::EventTraits>;  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Конструктор Event::Event (библиотека шаблонов C++ среды выполнения Windows)](../windows/event-event-constructor-windows-runtime-cpp-template-library.md)|Инициализирует новый экземпляр класса Event.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор Event::operator=](../windows/event-operator-assign-operator.md)|Присваивает указанную ссылку на событие текущему экземпляру Event.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HandleT`  
  
 `Event`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::wrl:: wrappers  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers](../windows/microsoft-wrl-wrappers-namespace.md)