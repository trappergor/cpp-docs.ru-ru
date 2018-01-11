---
title: "Метод ChainInterfaces::Verify | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::ChainInterfaces::Verify
dev_langs: C++
helpviewer_keywords: Verify method
ms.assetid: c591e130-8686-4130-ba69-1aaedc250038
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: d34d117091fd8807dfefda074e510910bf059560
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="chaininterfacesverify-method"></a>Метод ChainInterfaces::Verify
Проверяет, чтобы каждый интерфейс определены параметры шаблона `I0` через `I9` наследует от IUnknown или IInspectable и который `I0` наследует от `I1` через `I9`.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
WRL_NOTHROW __forceinline static void Verify();  
```  
  
## <a name="remarks"></a>Примечания  
 Если операция проверки завершается ошибкой, `static_assert` выдает сообщение об ошибке с описанием причины.  
  
## <a name="remarks"></a>Примечания  
 Параметры шаблона `I0` и `I1` являются обязательными, а параметры с `I2` до `I9` — необязательными.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** implements.h  
  
 **Пространство имен:** Microsoft::WRL  
  
## <a name="see-also"></a>См. также  
 [Структура ChainInterfaces](../windows/chaininterfaces-structure.md)