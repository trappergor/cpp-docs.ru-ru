---
title: Структура InterfaceTraits | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::InterfaceTraits
dev_langs:
- C++
helpviewer_keywords:
- InterfaceTraits structure
ms.assetid: ede0c284-19a7-4892-9738-ff3da4923d0a
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 4203fbb639b06e7e421809f9d901c70933d586d1
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33878688"
---
# <a name="interfacetraits-structure"></a>InterfaceTraits - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename I0  
>  
struct __declspec(novtable) InterfaceTraits;  
template<typename CloakedType>  
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
  
|Имя|Описание|  
|----------|-----------------|  
|`Base`|Синоним для параметра шаблона `I0`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод InterfaceTraits::CanCastTo](../windows/interfacetraits-cancastto-method.md)|Указывает ли заданный указатель может быть приведен к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToBase](../windows/interfacetraits-casttobase-method.md)|Приводит определенный указатель к указателю на `Base`.|  
|[Метод InterfaceTraits::CastToUnknown](../windows/interfacetraits-casttounknown-method.md)|Приводит определенный указатель на указатель на IUnknown.|  
|[Метод InterfaceTraits::FillArrayWithIid](../windows/interfacetraits-fillarraywithiid-method.md)|Назначает идентификатор интерфейса `Base` на элемент массива, заданного аргументом индекса.|  
|[Метод InterfaceTraits::Verify](../windows/interfacetraits-verify-method.md)|Проверяет, что базовый правильно производный.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Константа InterfaceTraits::IidCount](../windows/interfacetraits-iidcount-constant.md)|Содержит количество идентификаторов, связанного с текущим объектом InterfaceTraits интерфейса.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `InterfaceTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)