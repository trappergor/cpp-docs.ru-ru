---
title: Isbaseofstrict-структура | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs:
- C++
helpviewer_keywords:
- IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d4690c15adac7be66ca916b1fc0f769e6c50190c
ms.sourcegitcommit: 38af5a1bf35249f0a51e3aafc6e4077859c8f0d9
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/09/2018
ms.locfileid: "40017907"
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
template <  
   typename Base,  
   typename Derived  
>  
  
struct IsBaseOfStrict;  
template <  
   typename Base  
>  
struct IsBaseOfStrict<Base, Base>;  
```  
  
### <a name="parameters"></a>Параметры  
 *Base*  
 Базовый тип.  
  
 *Производные*  
 Производный тип.  
  
## <a name="remarks"></a>Примечания  
 Проверяет, является ли один тип базовым для другого.  
  
 Первый шаблон проверяет, является ли тип, производный от базового типа, который может дать **true** или **false**. Второй шаблон проверяет, является ли тип является производным от самого себя, которая всегда создает **false**.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание:|  
|----------|-----------------|  
|[Константа IsBaseOfStrict::value](../windows/isbaseofstrict-value-constant.md)|Указывает, является ли один тип базовым для другого.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `IsBaseOfStrict`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** internal.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Details](../windows/microsoft-wrl-details-namespace.md)