---
title: Issame-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsSame
dev_langs:
- C++
helpviewer_keywords:
- IsSame structure
ms.assetid: 1eddbc3f-3cc5-434f-8495-e4477e1f868e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: b63e3784529edf8957654511af53373fd80799ae
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40014264"
---
# <a name="issame-structure"></a>IsSame - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename T1,  
   typename T2  
>  
struct IsSame;  
template <  
   typename T1  
>  
struct IsSame<T1, T1>;  
```  
  
### <a name="parameters"></a>Параметры  
 *T1*  
 Тип.  
  
 *T2*  
 Другой тип.  
  
## <a name="remarks"></a>Примечания  
 Определяет, совпадают ли указанные типы друг с другом.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Константа IsSame::value](../windows/issame-value-constant.md)|Указывает, совпадают ли заданные типы друг с другом.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IsSame`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)