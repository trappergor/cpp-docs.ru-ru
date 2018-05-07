---
title: Класс Platform::Array | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Namespace not found::Platform
- VCCORLIB/Namespace not found::Platform::Array Constructors
- VCCORLIB/Namespace not found::Platform::Array::Value
dev_langs:
- C++
helpviewer_keywords:
- Platform::Array Class
ms.assetid: 7815ab40-88c5-42b0-83b8-081cef0cda31
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 4c6a326db5400d8dfb335f9c9e20867a26db59b0
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="platformarray-class"></a>Platform::Array - класс
Представляет изменяемый одномерный массив, который можно получать и передавать через двоичный интерфейс приложений (ABI).  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp    
template <typename T>  
private ref class Array<TArg, 1> :   
    public WriteOnlyArray<TArg, 1>,  
    public IBoxArray<TArg>   
```  
  
### <a name="members"></a>Участники  
 Platform::Array наследует все методы из [класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md) и реализует `Value` свойство [интерфейс Platform::IBoxArray](../cppcx/platform-iboxarray-interface.md).  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[Конструкторы массивов](#ctor)|Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.|  
  
### <a name="methods"></a>Методы  
 В разделе [класс Platform::WriteOnlyArray](../cppcx/platform-writeonlyarray-class.md).  
  
### <a name="properties"></a>Свойства  
  
|||  
|-|-|  
|[Array::Value](#value)|Получает дескриптор текущего массива.|  
  
### <a name="remarks"></a>Примечания  
 Класс Array является запечатанным и наследовать его нельзя.  
  
 Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и поэтому невозможно передать IVector < Platform::Array\<T >> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Дополнительные сведения о способе можно использовать Platform::Array и см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).  
  
 Система типов среды выполнения Windows не поддерживает концепцию массивов массивов и поэтому невозможно передать IVector < Platform::Array\<T >> в качестве возвращаемого значения или параметра метода. Для передачи массива массивов или последовательности массивов в ABI используйте `IVector<IVector<T>^>`.  
  
 Этот класс определен в заголовке vccorlib.h, который автоматически включается компилятором. Он отображается в Intellisense, но не в обозревателе объектов, поскольку нет открытого типа, определенного в platform.winmd.  
  
### <a name="requirements"></a>Требования  
 Параметр компилятора: **/ZW**  

 
## <a name="ctor"></a>  Конструкторы массивов
Инициализирует одномерный изменяемый массив типов, указанных в параметре шаблона класса *T*.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
Array(unsigned int size);  
Array(T* data, unsigned int size);    
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Параметр шаблона класса.  
  
 `size`  
 Количество элементов в массиве.  
  
 `data`  
 Указатель на массив данных типа `T`, используемый для инициализации данного объекта Array.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения о том, как создавать экземпляры Platform::Array см. в разделе [Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md).

## <a name="get"></a>  Array::Get-метод
Извлекает ссылку на элемент массива с указанным индексом.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp    
T& get(unsigned int index)  const;  
```  
  
#### <a name="parameters"></a>Параметры  
 `index`  
 Отсчитываемый от нуля индекс, указывающий на элемент в массиве. Минимальный индекс — 0, а максимальный — значение, заданное параметром `size` параметр в [конструктора Array](#ctor).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Элемент массива, заданный параметром `index`.  
  
## <a name="value"></a>  Свойство Array::value
Получает дескриптор текущего массива.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp 
property Array^ Value;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор текущего массива.  

## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)   
 [Классы Array и WriteOnlyArray](../cppcx/array-and-writeonlyarray-c-cx.md)