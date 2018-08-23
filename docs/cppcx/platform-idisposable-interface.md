---
title: Интерфейс Platform::IDisposable | Документация Майкрософт
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: f3899c25d71ad08cc058280271080c19d11222ed
ms.sourcegitcommit: 6f8dd98de57bb80bf4c9852abafef1c35a7600f1
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 08/22/2018
ms.locfileid: "42589790"
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
  
|Метод|Описание:|  
|------------|-----------------|  
|Ликвидировать|Используется для освобождения неуправляемых ресурсов.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform