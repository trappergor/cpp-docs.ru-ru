---
title: Класс значения Platform::sizet | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs:
- C++
helpviewer_keywords:
- Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8c69bf34a7965c098f6a656907071e0899b785b4
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformsizet-value-class"></a>Класс значения Platform::SizeT
Представляет размер объекта. SizeT — беззнаковый тип данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class SizeT sealed : ValueType  
```  
  
### <a name="members"></a>Участники  
  
|Член|Описание|  
|------------|-----------------|  
|[Конструктор SizeT::SizeT](#ctor)|Инициализирует новый экземпляр класса, используя указанное значение.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

 ## <a name="ctor"></a>  Конструктор SizeT::SizeT
Инициализирует новый экземпляр класса SizeT указанным значением.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
SizeT( uint32 value1 );   SizeT( void* value2 );  
```  
  
### <a name="parameters"></a>Параметры  
 value1  
 32-битовое значение без знака.  
  
 value2  
 Указатель на 32-разрядное значение без знака.  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)