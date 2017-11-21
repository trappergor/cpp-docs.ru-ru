---
title: "Структура MixIn | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::MixIn
dev_langs: C++
helpviewer_keywords: MixIn structure
ms.assetid: 47e2df9b-3a2e-4ae8-8ba3-b1fd3aa73566
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e1df2de0a8c645b957a5c3e93f8c4ebbb3b2fb94
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="mixin-structure"></a>MixIn - структура
Гарантирует, что класс среды выполнения является производным от интерфейсов среды выполнения Windows, если таковые имеются, а затем от интерфейсов классической модели COM.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
template<  
   typename Derived,  
   typename MixInType,  
   bool hasImplements = __is_base_of(Details::ImplementsBase,  
   MixInType)  
>  
struct MixIn;  
```  
  
#### <a name="parameters"></a>Параметры  
 `Derived`  
 Тип, производный от [реализует](../windows/implements-structure.md) структуры.  
  
 `MixInType`  
 Базовый тип.  
  
 `hasImplements`  
 Значение `true`, если `MixInType` является производным от текущей реализации базового типа; в противном случае — значение `false`.  
  
## <a name="remarks"></a>Примечания  
 Если класс является производным от среды выполнения Windows и интерфейсов класса модели COM, список объявления класса сначала должен перечислить все интерфейсы среды выполнения Windows, и затем любой классического COM интерфейсы. Параметр MixIn проверяет, определены ли интерфейсы в правильном порядке.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 `MixIn`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Microsoft::WRL](../windows/microsoft-wrl-namespace.md)