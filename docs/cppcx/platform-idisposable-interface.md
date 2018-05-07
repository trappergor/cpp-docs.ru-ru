---
title: Интерфейс Platform::IDisposable | Документы Microsoft
ms.custom: ''
ms.date: 02/03/2017
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::IDisposable
dev_langs:
- C++
helpviewer_keywords:
- Platform::IDisposable Interface
ms.assetid: f4344056-7030-42ed-bc98-b140edffddcd
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 68c5425d5d65acc194287a97068df7da15f37275
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformidisposable-interface"></a>Интерфейс Platform::IDisposable
Используется для освобождения неуправляемых ресурсов.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public interface class IDisposable  
```  
  
## <a name="attributes"></a>Атрибуты  
 **GuidAttribute**(«de0cbaea-8065-4a45-b196-c9d443f9bab3»)  
  
 **VersionAttribute**(NTDDI_WIN8)  
  
### <a name="members"></a>Участники  
 Интерфейс IDisposable наследует от интерфейса IUnknown. Интерфейс IDisposable также имеет следующие типы членов.  
  
 **Методы**  
  
 Интерфейс IDisposable содержит следующие методы.  
  
|Метод|Описание|  
|------------|-----------------|  
|Ликвидировать|Используется для освобождения неуправляемых ресурсов.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform