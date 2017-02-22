---
title: "Структура InterfaceTraits | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "implements/Microsoft::WRL::Details::InterfaceTraits"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InterfaceTraits - структура"
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Структура InterfaceTraits
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Предназначено для поддержки инфраструктуры WRL, а не для непосредственного использования в коде.  
  
## Синтаксис  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
  
template<  
   typename CloakedType  
>  
struct __declspec(novtable) InterfaceTraits<CloakedIid<CloakedType>>;  
  
template<>  
struct __declspec(novtable) InterfaceTraits<Nil>;  
```  
  
#### Параметры  
 `I0`  
 Имя интерфейса.  
  
 `CloakedType`  
 Для RuntimeClass, Implements и ChainInterfaces, интерфейс, который не может быть в списке поддерживаемых идентификаторов интерфейса.  
  
## Примечания  
 Реализует общие характеристики интерфейса.  
  
 Второй шаблон является специализацией для замаскированных интерфейсов.  Третий шаблон является специализацией для параметров Nil.  
  
## Члены  
  
### Общедоступные Typedefs  
  
|Имя|Описание|  
|---------|--------------|  
|`Base`|Синоним для параметра шаблона `I0`.|  
  
### Открытые методы  
  
|Имя|Описание|  
|---------|--------------|  
|[Метод InterfaceTraits::CanCastTo](../Topic/InterfaceTraits::CanCastTo%20Method.md)|Показывает, можно ли определенный указатель привести к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToBase](../windows/interfacetraits-casttobase-method.md)|Приводит определенный указатель к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToUnknown](../windows/interfacetraits-casttounknown-method.md)|Приводит определенный указатель к указателю на IUnknown.|  
|[Метод InterfaceTraits::FillArrayWithIid](../windows/interfacetraits-fillarraywithiid-method.md)|Присваивает идентификатор интерфейса `Base` к элементу массива, указанному аргументом индекса.|  
|[Метод InterfaceTraits::Verify](../Topic/InterfaceTraits::Verify%20Method.md)|Проверяет, что Base наследуется правильно.|  
  
### Открытые константы  
  
|Имя|Описание|  
|---------|--------------|  
|[Константа InterfaceTraits::IidCount](../Topic/InterfaceTraits::IidCount%20Constant.md)|Содержит количество идентификаторов интерфейса, связанных с текущим объектом InterfaceTraits.|  
  
## Иерархия наследования  
 `InterfaceTraits`  
  
## Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL::Details  
  
## См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)