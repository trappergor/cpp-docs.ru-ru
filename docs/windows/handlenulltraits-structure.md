---
title: "Структура HANDLENullTraits | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleTraits::HANDLENullTraits
dev_langs: C++
helpviewer_keywords: HANDLENullTraits structure
ms.assetid: 88a29a14-c516-40cb-a0ca-ee897a668623
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: b1e28415cf6f0e5f29d50349cd38fe4b18cfe812
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="handlenulltraits-structure"></a>HANDLENullTraits - структура
Определяет общие характеристики дескриптора неинициализированным.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
struct HANDLENullTraits;  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-typedefs"></a>Общедоступные определения типов  
  
|Имя|Описание|  
|----------|-----------------|  
|`Type`|Синоним для HANDLE.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Метод HANDLENullTraits::Close](../windows/handlenulltraits-close-method.md)|Закрывает указанный дескриптор.|  
|[Метод HANDLENullTraits::GetInvalidValue](../windows/handlenulltraits-getinvalidvalue-method.md)|Представляет недопустимый дескриптор.|  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `HANDLENullTraits`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** corewrappers.h  
  
 **Пространство имен:** Microsoft::WRL::Wrappers::HandleTraits  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL::Wrappers::HandleTraits](../windows/microsoft-wrl-wrappers-handletraits-namespace.md)