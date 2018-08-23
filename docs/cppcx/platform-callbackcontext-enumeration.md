---
title: Перечисление Platform::CallbackContext | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 4b80fe7749fdb2f91e300cff007c01001edfa557
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42603042"
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