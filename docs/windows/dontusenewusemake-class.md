---
title: "Класс DontUseNewUseMake | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::DontUseNewUseMake
dev_langs: C++
helpviewer_keywords: DontUseNewUseMake class
ms.assetid: 8b38d07b-fc14-4cea-afb9-4c1a7dde0093
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: c09276fb761dcd1f2f5be78afa40606e262aa3e1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="dontusenewusemake-class"></a>DontUseNewUseMake - класс
Поддерживает инфраструктуру WRL и не предназначен для использования непосредственно из программного кода.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class DontUseNewUseMake;  
```  
  
## <a name="remarks"></a>Примечания  
 Предотвращает использование оператора `new` в RuntimeClass. Следовательно, необходимо использовать [функция](../windows/make-function.md) вместо него.  
  
## <a name="members"></a>Участники  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[Оператор DontUseNewUseMake::operator new](../windows/dontusenewusemake-operator-new-operator.md)|Перегружает оператор `new` и препятствует его использованию в RuntimeClass.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `DontUseNewUseMake`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::wrl:: Details  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::wrl:: Details](../windows/microsoft-wrl-details-namespace.md)   
 [Функция Make](../windows/make-function.md)