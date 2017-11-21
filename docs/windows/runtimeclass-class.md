---
title: "Класс RuntimeClass | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass
dev_langs: C++
helpviewer_keywords: RuntimeClass class
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e757712b360ff3ed4de12d8236c75a691a1f0c7c
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclass-class"></a>Класс RuntimeClass
Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанную среду выполнения Windows, классическую COM-модель и поддержку слабых ссылок.  
  
 Вы обычно производные типы WRL из `RuntimeClass` , так как этот класс реализует `AddRef`, `Release`, и `QueryInterface`, и помогает управлять общее количество ссылок на модуль.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   typename I0,  
   typename I1 = Details::Nil,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
class RuntimeClass : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8, I9>::TypeT, RuntimeClassFlags<WinRt>>;  
  
template <  
   unsigned int classFlags,  
   typename I0,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8  
>  
class RuntimeClass<RuntimeClassFlags<classFlags>, I0, I1, I2, I3, I4, I5, I6, I7, I8> : public Details::RuntimeClass<typename Details::InterfaceListHelper<I0, I1, I2, I3, I4, I5, I6, I7, I8>::TypeT, RuntimeClassFlags<classFlags> >;  
```  
  
#### <a name="parameters"></a>Параметры  
 `I0`  
 Интерфейс нулевой идентификатор. (Обязательный)  
  
 `I1`  
 Первый идентификатор интерфейса. (Необязательный параметр).  
  
 `I2`  
 Второй идентификатор интерфейса. (Необязательный параметр).  
  
 `I3`  
 Третий идентификатор интерфейса. (Необязательный параметр).  
  
 `I4`  
 Четвертый идентификатор интерфейса. (Необязательный параметр).  
  
 `I5`  
 Пятый идентификатор интерфейса. (Необязательный параметр).  
  
 `I6`  
 Шестой идентификатор интерфейса. (Необязательный параметр).  
  
 `I7`  
 Седьмой идентификатор интерфейса. (Необязательный параметр).  
  
 `I8`  
 Идентификатор интерфейса восьмого (Необязательный параметр).  
  
 `I9`  
 Девятый идентификатор интерфейса. (Необязательный параметр).  
  
 `classFlags`  
 Сочетание одного или нескольких [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) значений перечисления.  `__WRL_CONFIGURATION_LEGACY__` Макрос можно определить таким образом, чтобы изменить значение по умолчанию classFlags для всех классов среды выполнения в проекте. Если определено, RuntimeClass экземпляры являются негибкий dy по умолчанию. Если не определен, RuntimeClass экземпляры являются гибкими по умолчанию. Чтобы избежать неоднозначности всегда указывать RuntimeClassType::FtmBase или RuntimeClassType::InhibitFtmBase.
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструктор RuntimeClass::RuntimeClass](../windows/runtimeclass-runtimeclass-constructor.md)|Инициализирует текущий экземпляр класса RuntimeClass.|  
|[Деструктор RuntimeClass::~RuntimeClass](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Деинициализирует текущий экземпляр класса RuntimeClass.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
 `I0`  
  
 `RuntimeClassBase`  
  
 `ImplementsHelper`  
  
 `DontUseNewUseMake`  
  
 `RuntimeClassFlags`  
  
 `RuntimeClassBaseT`  
  
 `RuntimeClass`  
  
 `RuntimeClass`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)
