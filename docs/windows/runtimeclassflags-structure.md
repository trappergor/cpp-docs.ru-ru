---
title: Структура RuntimeClassFlags | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::RuntimeClassFlags
dev_langs:
- C++
helpviewer_keywords:
- RuntimeClassFlags structure
ms.assetid: 7098d605-bd14-4d51-82f4-3def8296a938
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 05166be14680b14d704095f5f1c9375bd97da7d5
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/08/2018
ms.locfileid: "33892030"
---
# <a name="runtimeclassflags-structure"></a>RuntimeClassFlags - структура
Содержит тип экземпляра класса [RuntimeClass](../windows/runtimeclass-class.md).  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template <  
   unsigned int flags  
>  
struct RuntimeClassFlags;  
```  
  
#### <a name="parameters"></a>Параметры  
 `flags`  
 Объект [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constants"></a>Открытые константы  
  
|name|Описание|  
|----------|-----------------|  
|[Константа RuntimeClassFlags::value](../windows/runtimeclassflags-value-constant.md)|Содержит [runtimeclasstype-перечисление](../windows/runtimeclasstype-enumeration.md) значение.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `RuntimeClassFlags`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)