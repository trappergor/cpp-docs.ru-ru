---
title: "Platform::callbackcontext-перечисление | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::CallbackContext
dev_langs:
- C++
helpviewer_keywords:
- Platform::CallbackContext Enumeration
ms.assetid: 60e0c7cb-5d8f-482a-bdca-ca9335ae4899
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 9f9d34f7ef8a953ce60972c27b34e257ea66d62d
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 02/14/2018
---
# <a name="platformcallbackcontext-enumeration"></a>Platform::CallbackContext - перечисление
Указывает контекст потока, в котором выполняется функция обратного вызова (обработчик события).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
enum class CallbackContext {};  
```  
  
### <a name="members"></a>Участники  
  
|Код типа|Описание:|  
|---------------|-----------------|  
|Любой|Функция обратного вызова может выполняться в любом контексте потока.|  
|То же|Функция обратного вызова может выполняться в контексте потока, запустившего асинхронную операцию.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd