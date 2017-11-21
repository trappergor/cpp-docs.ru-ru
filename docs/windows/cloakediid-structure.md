---
title: "Структура CloakedIid | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::CloakedIid
dev_langs: C++
helpviewer_keywords: CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5a10752fecadaf3a7f044e3c563931ae3cdbe1b4
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="cloakediid-structure"></a>CloakedIid - структура
Указывает шаблонам RuntimeClass, Implements и ChainInterfaces, что заданный интерфейс недоступен в списке IID.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename T  
>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Интерфейс, который является скрытым (замаскированные).  
  
## <a name="remarks"></a>Примечания  
 Ниже приведен пример использования CloakedIid: `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)