---
title: "Класс Platform::Box | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.prod: windows-client-threshold
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: VCCORLIB/Platform::Box
dev_langs: C++
ms.assetid: b3d7ea37-e98a-4fbc-80b0-ad35e50250c6
caps.latest.revision: "7"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ac0940d9a7277b7b3f5b66e8d27750a593081471
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="platformbox-class"></a>Класс Platform::Box
Позволяет сохранять тип значения, такой как `Windows::Foundation::DateTime` , или скалярный тип, такой как `int` , в типе `Platform::Object` . Как правило, нет необходимости использовать `Box` явным образом, так как процесс упаковки выполняется неявно при приведении значения типа к `Object^`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
ref class Box abstract;  
```  
  ### <a name="remarks"></a>Примечания  
  
### <a name="requirements"></a>Требования  
 **Заголовок:** vccorlib.h  
  
 **Пространство имен:** Platform
|Член|Описание:|  
|------------|-----------------|
|[Box](#ctor)|Создает `Box` который может инкапсулировать значение указанного типа.|
|[оператор поле&lt;const T&gt;^](#box-const-t)|Позволяет осуществлять преобразования-упаковки класса значений `const` `T` или `enum` класса `T` в `Box<T>`.|
|[оператор поле&lt;const volatile T&gt;^](#box-const-volatile-t)|Позволяет осуществлять преобразования-упаковки из класса значений `const volatile` `T` или `enum` типа `T` в `Box<T>`. |
|[оператор поле&lt;T&gt;^](#box-t)|Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`.|
|[оператор поле&lt;volatile T&gt;^](#box-volatile-t)|Позволяет осуществлять преобразования-упаковки из класса значений `volatile` `T` или `enum` типа `T` в `Box<T>`.|
|[Box::operator T](#t)|Позволяет осуществлять преобразования-упаковки класса значений `T` или `enum` класса `T` в `Box<T>`.| 
## <a name="ctor"></a>Конструктор Box::Box
Создает `Box` , может инкапсулировать значение указанного типа. | |[ Значение свойства](#value)| Возвращает значение, которое инкапсулируется в `Box` объекта. |  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Box(T valueArg);  
```  
  
### <a name="parameters"></a>Параметры  
 `valueArg`  
 Тип упаковываемого значения — например, `int`, `bool`, `float64`, `DateTime`.  
  

## <a name="box-const-t"></a>Box::operator Box&lt;const T&gt;^ оператор
Позволяет осуществлять преобразования-упаковки класса значений `const` `T` или `enum` класса `T` в `Box<T>`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Любой класс значений, структура значений или тип перечисления. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::Box<T>^` экземпляр, который представляет исходное значение, упакованное в класс ref.  
  
## <a name="box-const-volatile-t"></a>Box::operator Box&lt;const volatile T&gt;^ оператор
Позволяет осуществлять преобразования-упаковки из класса значений `const volatile` `T` или `enum` типа `T` в `Box<T>`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
operator Box<const volatile T>^(const volatile T valueType);  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::Box<T>^` экземпляр, который представляет исходное значение, упакованное в класс ref.  
  
## <a name="box-t"></a>Box::operator Box&lt;T&gt;^ оператор
Позволяет осуществлять преобразования-упаковки класса значений `T` в `Box<T>`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
operator Box<const T>^(const T valueType);  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::Box<T>^` экземпляр, который представляет исходное значение, упакованное в класс ref.  
  
## <a name="box-volatile-t"></a>Box::operator Box&lt;volatile T&gt;^ оператор
Позволяет осуществлять преобразования-упаковки из класса значений `volatile` `T` или `enum` типа `T` в `Box<T>`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
operator Box<volatile T>^(volatile T valueType);  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::Box<T>^` экземпляр, который представляет исходное значение, упакованное в класс ref.  
  
## <a name="t"></a>Оператор Box::operator T
Позволяет осуществлять преобразования-упаковки класса значений `T` или `enum` класса `T` в `Box<T>`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
operator Box<T>^(T valueType);  
```  
  
### <a name="parameters"></a>Параметры  
 `T`  
 Любой тип перечисления, класс значений или структура значений. Включает встроенные типы в [пространство имен по умолчанию](../cppcx/default-namespace.md).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::Box<T>^` экземпляр, который представляет исходное значение, упакованное в класс ref.  
  

## <a name="value"></a>Свойство Box::value
Возвращает значение, которое инкапсулируется в объекте `Box`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
virtual property T Value{  
   T get();  
}  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает упакованное значение с тем же типом, который у него был до упаковки.  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Упаковка-преобразование](../cppcx/boxing-c-cx.md)