---
title: "Структура IsBaseOfStrict | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: internal/Microsoft::WRL::Details::IsBaseOfStrict
dev_langs: C++
helpviewer_keywords: IsBaseOfStrict structure
ms.assetid: 6fed7366-c8d4-4991-b4fb-43ed93f8e1bf
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8a8e40bec0f4dedf02aab14b2c8072ccc3e60bbb
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="isbaseofstrict-structure"></a>IsBaseOfStrict - структура
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
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
  
#### <a name="parameters"></a>Параметры  
 `Base`  
 Базовый тип.  
  
 `Derived`  
 Производный тип.  
  
## <a name="remarks"></a>Примечания  
 Проверяет, является ли один тип базовым для другого.  
  
 Первый шаблон определяет, является ли тип, производный от базового типа, что может обеспечить **true** или **false**. Второй шаблон проверяет, является ли тип является производным от самого себя, который всегда создает **false**.  
  
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