---
title: "Класс значения Platform::IntPtr | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/PlatformIntPtr::IntPtr
- VCCORLIB/PlatformIntPtr::op_explicit Operator
- VCCORLIB/PlatformIntPtr::ToInt32
dev_langs: C++
helpviewer_keywords: Platform::IntPtr Struct
ms.assetid: 6c0326e8-edfd-4e53-a963-240b845dcde8
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: 4bd0fcdf8f7b7f825a087a2176babeb59bac4f05
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformintptr-value-class"></a>Класс значения Platform::IntPtr
Представляет указатель или дескриптор числа со знаком, размер которого зависит от платформы (32-разрядная или 64-разрядная).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public value struct IntPtr  
```  
  
### <a name="members"></a>Члены  
 Класс IntPtr имеет следующие члены:  
  
|Член|Описание|  
|------------|-----------------|  
|[IntPtr::IntPtr](#ctor)|Инициализирует новый экземпляр класса IntPtr.|  
|[Оператор IntPtr::op_explicit](#op-explicit)|Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.|  
|[IntPtr::ToInt32](#toint32)|Преобразует текущий объект IntPtr в 32-разрядное целое число.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

## <a name="ctor"> </a> IntPtr::IntPtr - конструктор
Инициализирует новый экземпляр класса IntPtr, используя указанное значение.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
IntPtr( __int64 handle-or-pointer );   IntPtr( void* value );   IntPtr( int 32-bit_value );  
```  
  
### <a name="parameters"></a>Параметры  
 значение  
 64-разрядный дескриптор или указатель, указатель на 64-разрядное значение или 32-разрядное значение, которое можно преобразовать в 64-разрядное.  
  


## <a name="op-explicit"> </a> Оператор IntPtr::op_explicit
Преобразует указанный параметр в объект IntPtr или указатель на значение IntPtr.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
static IntPtr::operator IntPtr( void* value1);   static IntPtr::operator IntPtr( int value2);   static IntPtr::operator void*( IntPtr value3 );  
```  
  
### <a name="parameters"></a>Параметры  
 value1  
 Указатель на дескриптор или IntPtr.  
  
 value2  
 32-битовое целое число, которое можно преобразовать в IntPtr.  
  
 value3  
 Объект IntPtr.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Первый и второй операторы возвращают IntPtr. Третий оператор возвращает указатель на значение, представленное текущим объектом IntPtr.  
  


## <a name="toint32"></a> Метод IntPtr::ToInt32
Преобразует текущее значение IntPtr в 32-битовое целое число.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
int32 IntPtr::ToInt32();  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 32-битовое целое число.  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)