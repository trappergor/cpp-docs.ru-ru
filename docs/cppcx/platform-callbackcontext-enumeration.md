---
title: Platform::callbackcontext-перечисление | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 757de5f686bb809a5d2fb159a3ee547a20edc982
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext - перечисление
Указывает контекст потока, в котором выполняется функция обратного вызова (обработчик события).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Участники  
  
|Код типа|Описание|  
|---------------|-----------------|  
|Любой|Функция обратного вызова может выполняться в любом контексте потока.|  
|То же|Функция обратного вызова может выполняться в контексте потока, запустившего асинхронную операцию.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd