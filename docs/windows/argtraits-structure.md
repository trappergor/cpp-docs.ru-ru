---
title: "Структура ArgTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- event/Microsoft::WRL::Details::ArgTraits
dev_langs:
- C++
helpviewer_keywords:
- ArgTraits structure
ms.assetid: 58ae4115-c1bc-48c8-b01b-e60554841c30
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 64ec29d674f6213992fbb1424093931b20ed45b3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="argtraits-structure"></a>ArgTraits - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename TMemberFunction  
>  
struct ArgTraits;  
template<  
   typename TDelegateInterface  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(void)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8)>;  
template<  
   typename TDelegateInterface,  
   typename TArg1,  
   typename TArg2,  
   typename TArg3,  
   typename TArg4,  
   typename TArg5,  
   typename TArg6,  
   typename TArg7,  
   typename TArg8,  
   typename TArg9  
>  
struct ArgTraits<HRESULT (STDMETHODCALLTYPE TDelegateInterface::*)(TArg1, TArg2, TArg3, TArg4, TArg5, TArg6, TArg7, TArg8, TArg9)>;  
```  
  
#### <a name="parameters"></a>Параметры  
 `TMemberFunction`  
 Параметр имени типа для структуры ArgTraits, который не должен соответствовать какой-либо сигнатуре метода Invoke.  
  
 `TDelegateInterface`  
 Интерфейс делегата.  
  
 `TArg1`  
 Тип первого аргумента метода Invoke.  
  
 `TArg2`  
 Тип второго аргумента метода Invoke.  
  
 `TArg3`  
 Тип третьего аргумента метода Invoke.  
  
 `TArg4`  
 Тип четвертого аргумента метода Invoke.  
  
 `TArg5`  
 Тип пятого аргумента метода Invoke.  
  
 `TArg6`  
 Тип шестого аргумента метода Invoke.  
  
 `TArg7`  
 Тип седьмого аргумента метода Invoke.  
  
 `TArg8`  
 Тип восьмого аргумента метода Invoke.  
  
 `TArg9`  
 Тип девятого аргумента метода Invoke.  
  
## <a name="remarks"></a>Примечания  
 Структура `ArgTraits` объявляет указанный интерфейс делегата и анонимную функцию-член, которая принимает указанное число параметров.  
  
## <a name="members"></a>Участники  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание:|  
|----------|-----------------|  
|`Arg1Type`|Typedef для TArg1.|  
|`Arg2Type`|Typedef для TArg2.|  
|`Arg3Type`|Typedef для TArg3.|  
|`Arg4Type`|Typedef для TArg4.|  
|`Arg5Type`|Typedef для TArg5.|  
|`Arg6Type`|Typedef для TArg6.|  
|`Arg7Type`|Typedef для TArg7.|  
|`Arg8Type`|Typedef для TArg8.|  
|`Arg9Type`|Typedef для TArg9.|  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Константа ArgTraits::args](../windows/argtraits-args-constant.md)|Содержит счетчик количества параметров метода Invoke для интерфейса делегата.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `ArgTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** event.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)