---
title: "Структура InterfaceTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs: C++
helpviewer_keywords: InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 1c28c7c1eef2fc278a0667ec4b7c635005331467
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="interfacetraits-structure"></a>InterfaceTraits - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
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
  
#### <a name="parameters"></a>Параметры  
 `I0`  
 Имя интерфейса.  
  
 `CloakedType`  
 Для RuntimeClass, Implements и ChainInterfaces интерфейс, который не будет в списке поддерживаемых идентификаторов интерфейсов.  
  
## <a name="remarks"></a>Примечания  
 Реализует общие характеристики интерфейса.  
  
 Второй шаблон является специализацией замаскированных интерфейсов. Третий шаблон является специализацией Nil параметров.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`Base`|Синоним для параметра шаблона `I0`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Метод InterfaceTraits::CanCastTo](../windows/interfacetraits-cancastto-method.md)|Указывает ли заданный указатель может быть приведен к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToBase](../windows/interfacetraits-casttobase-method.md)|Приводит определенный указатель к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToUnknown](../windows/interfacetraits-casttounknown-method.md)|Приводит определенный указатель на указатель на IUnknown.|  
|[Метод InterfaceTraits::FillArrayWithIid](../windows/interfacetraits-fillarraywithiid-method.md)|Назначает идентификатор интерфейса `Base` на элемент массива, заданного аргументом индекса.|  
|[Метод InterfaceTraits::Verify](../windows/interfacetraits-verify-method.md)|Проверяет, что базовый правильно производный.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Константа InterfaceTraits::IidCount](../windows/interfacetraits-iidcount-constant.md)|Содержит количество идентификаторов, связанного с текущим объектом InterfaceTraits интерфейса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)