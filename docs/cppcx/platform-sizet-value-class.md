---
title: "Класс значения Platform::sizet | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/PlatformSizeT::SizeT constructor
dev_langs: C++
helpviewer_keywords: Platform::SizeT Struct
ms.assetid: 0803612c-8ba1-430c-9b7b-1bebae88608d
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 18001661b0862f19e3c002f4c4e60efdf68c9e30
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformsizet-value-class"></a>Класс значения Platform::SizeT
Представляет размер объекта. SizeT — беззнаковый тип данных.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public ref class SizeT sealed : ValueType  
```  
  
### <a name="members"></a>Члены  
  
|Член|Описание|  
|------------|-----------------|  
|[Конструктор SizeT::SizeT](#ctor)|Инициализирует новый экземпляр класса, используя указанное значение.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

 ## <a name="ctor"></a>Конструктор SizeT::SizeT
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