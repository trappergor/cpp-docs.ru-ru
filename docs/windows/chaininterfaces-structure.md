---
title: "Структура ChainInterfaces | Microsoft Docs"
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
  - "implements/Microsoft::WRL::ChainInterfaces"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ChainInterfaces - структура"
ms.assetid: d7415b59-5468-4bef-a3fd-8d82b12f0e9c
caps.latest.revision: 3
caps.handback.revision: 3
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Структура ChainInterfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Определяет функции проверки и инициализации, которые можно применить к набору идентификаторов интерфейсов.  
  
## Синтаксис  
  
```  
template <  
   typename I0,  
   typename I1,  
   typename I2 = Details::Nil,  
   typename I3 = Details::Nil,  
   typename I4 = Details::Nil,  
   typename I5 = Details::Nil,  
   typename I6 = Details::Nil,  
   typename I7 = Details::Nil,  
   typename I8 = Details::Nil,  
   typename I9 = Details::Nil  
>  
struct ChainInterfaces : I0;  
template <  
   typename DerivedType,  
   typename BaseType,  
   bool hasImplements,  
   typename I1,  
   typename I2,  
   typename I3,  
   typename I4,  
   typename I5,  
   typename I6,  
   typename I7,  
   typename I8,  
   typename I9  
>  
struct ChainInterfaces<MixIn<DerivedType, BaseType, hasImplements>, I1, I2, I3, I4, I5, I6, I7, I8, I9>;  
```  
  
#### Параметры  
 `I0`  
 \(Обязательный\) Идентификатор интерфейса 0.  
  
 `I1`  
 \(Обязательный\) Идентификатор интерфейса 1.  
  
 `I2`  
 \(Необязательный\). Идентификатор интерфейса 2.  
  
 `I3`  
 \(Необязательный\). Идентификатор интерфейса 3.  
  
 `I4`  
 \(Необязательный\). Идентификатор интерфейса 4.  
  
 `I5`  
 \(Необязательный\). Идентификатор интерфейса 5.  
  
 `I6`  
 \(Необязательный\). Идентификатор интерфейса 6.  
  
 `I7`  
 \(Необязательный\). Идентификатор интерфейса 7.  
  
 `I8`  
 \(Необязательный\). Идентификатор интерфейса 8.  
  
 `I9`  
 \(Необязательный\). Идентификатор интерфейса 9.  
  
 `DerivedType`  
 Производный тип.  
  
 `BaseType`  
 Базовый тип производного типа.  
  
 `hasImplements`  
 Логическое значение, если `true`, то нельзя использовать структуру [MixIn](../windows/mixin-structure.md) с классом, который не является производным от структуры [Implements](../Topic/Implements%20Structure.md).  
  
## Члены  
  
### Защищенные методы  
  
|Name|Описание|  
|----------|--------------|  
|[Метод ChainInterfaces::CanCastTo](../Topic/ChainInterfaces::CanCastTo%20Method.md)|Указывает, может ли идентификатор указанного интерфейса быть приведен к каждой из спецификаций, определенных параметрами шаблонов ChainInterface.|  
|[Метод ChainInterfaces::CastToUnknown](../windows/chaininterfaces-casttounknown-method.md)|Приводит указатель интерфейса типа, указанного в параметре шаблона `I0` к указателю на интерфейс IUnknown.|  
|[Метод ChainInterfaces::FillArrayWithIid](../Topic/ChainInterfaces::FillArrayWithIid%20Method.md)|Хранит идентификатор интерфейса, заданный параметром шаблона `I0` в указанное место в указанном массиве идентификаторов интерфейса.|  
|[Метод ChainInterfaces::Verify](../windows/chaininterfaces-verify-method.md)|Проверяет, что каждый интерфейс, заданный параметрами `I0` шаблона через `I9` наследуется от IUnknown и\/или IInspectable, и что `I0` наследуется от `I1` через `I9`.|  
  
### Защищенные константы  
  
|Name|Описание|  
|----------|--------------|  
|[Константа ChainInterfaces::IidCount](../windows/chaininterfaces-iidcount-constant.md)|Общее число идентификаторов интерфейса, содержащихся в интерфейсах, указанных параметрами `I0` шаблона через `I9`.|  
  
## Иерархия наследования  
 `I0`  
  
 `ChainInterfaces`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)