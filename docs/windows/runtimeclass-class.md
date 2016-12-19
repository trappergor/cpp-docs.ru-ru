---
title: "Класс RuntimeClass | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::RuntimeClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RuntimeClass - класс"
ms.assetid: d52f9d1a-98e5-41f2-a143-8fb629dd0727
caps.latest.revision: 5
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Класс RuntimeClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Представляет экземпляр класса, который наследует указанное число интерфейсов и предоставляет указанный [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], классическую COM\-модель и поддержку слабых ссылок.  
  
 Как правило, WRL\-типы наследуются от `RuntimeClass`, поскольку этот класс реализует `AddRef`, `Release` и `QueryInterface` и помогает управлять общим числом ссылок в модуле.  
  
## Синтаксис  
  
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
  
#### Параметры  
 `I0`  
 Идентификатор нулевого интерфейса. \(Обязательно\)  
  
 `I1`  
 Идентификатор первого интерфейса. \(Необязательный параметр\)  
  
 `I2`  
 Идентификатор второго интерфейса. \(Необязательный параметр\)  
  
 `I3`  
 Идентификатор третьего интерфейса. \(Необязательный параметр\)  
  
 `I4`  
 Идентификатор четвертого интерфейса. \(Необязательный параметр\)  
  
 `I5`  
 Идентификатор пятого интерфейса. \(Необязательный параметр\)  
  
 `I6`  
 Идентификатор шестого интерфейса. \(Необязательный параметр\)  
  
 `I7`  
 Идентификатор седьмого интерфейса. \(Необязательный параметр\)  
  
 `I8`  
 Идентификатор восьмого интерфейса. \(Необязательный параметр\)  
  
 `I9`  
 Идентификатор девятого интерфейса. \(Необязательный параметр\)  
  
 `classFlags`  
 Сочетание одного или нескольких значений перечисления [RuntimeClassType](../windows/runtimeclasstype-enumeration.md).  
  
## Члены  
  
### Открытые конструкторы  
  
|Name|Описание|  
|----------|--------------|  
|[Конструктор RuntimeClass::RuntimeClass](../windows/runtimeclass-runtimeclass-constructor.md)|Инициализирует текущий экземпляр класса RuntimeClass.|  
|[Деструктор RuntimeClass::~RuntimeClass](../windows/runtimeclass-tilde-runtimeclass-destructor.md)|Деинициализирует текущий экземпляр класса RuntimeClass.|  
  
## Иерархия наследования  
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
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)