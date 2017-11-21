---
title: "Класс Platform::StringReference | Документы Microsoft"
ms.custom: 
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- VCCORLIB/Platform::StringReference::StringReference
- VCCORLIB/Platform::StringReference::Data
- VCCORLIB/Platform::StringReference::Length
- VCCORLIB/Platform::StringReference::GetHSTRING
- VCCORLIB/Platform::StringReference::GetString
dev_langs: C++
ms.assetid: 2d09c7ec-0f16-458e-83ed-7225a1b9221e
caps.latest.revision: "4"
author: ghogen
ms.author: ghogen
manager: ghogen
ms.openlocfilehash: bf096ef9849856e9995ff634d7aca26cd7f3f8e9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
---
# <a name="platformstringreference-class"></a>Класс Platform::StringReference
Тип оптимизации, который можно использовать для передачи строковых данных из входных параметров `Platform::String^` в другие методы с минимальным числом операций копирования.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
class StringReference  
```  
  
### <a name="remarks"></a>Примечания  
  
### <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[StringReference::StringReference](#ctor)|Два конструктора для создания экземпляров `StringReference`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[StringReference::Data](#data)|Возвращает строковые данные как массив значений char16.|  
|[StringReference::Length](#length)|Возвращает число символов в строке.|  
|[StringReference::GetHSTRING](#gethstring)|Возвращает строковые данные как HSTRING.|  
|[StringReference::GetString](#getstring)|Возвращает строковые данные как `Platform::String^`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[StringReference::operator =](#operator-assign)|Присваивает `StringReference` новому экземпляру `StringReference` .|  
|[Stringreference:: operator()](#operator-call)|Преобразует `StringReference` в `Platform::String^`.|  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Заголовок:** vccorlib.h  

## <a name="data"></a>Метод StringReference::Data
Возвращает содержимое этого `StringReference` как массив значений char16.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
const ::default::char16 * Data() const  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Массив текстовых символов ЮНИКОДА char16.  
  


## <a name="gethstring"></a>Метод StringReference::GetHSTRING
Возвращает содержимое строки как `__abi_HSTRING`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
__abi_HSTRING GetHSTRING() const  
  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `__abi_HSTRING`, который содержит строковые данные.  
  
### <a name="remarks"></a>Примечания  
  


## <a name="getstring"></a>Метод StringReference::GetString
Возвращает содержимое строки как `Platform::String^`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
__declspec(no_release_return) __declspec(no_refcount)  
    ::Platform::String^ GetString() const  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект `Platform::String^`, который содержит строковые данные.  

## <a name="length"></a>Метод StringReference::Length
Возвращает число символов в строке.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
unsigned int Length() const  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Целое число без знака, указывающее число символов в строке.  
  
### <a name="remarks"></a>Примечания  
  


## <a name="operator-assign"></a>StringReference::operator =-оператор
Присваивает указанный объект текущему объекту `StringReference`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
StringReference& operator=(const StringReference& __fstrArg);  
StringReference& operator=(const ::default::char16* __strArg);    
```  
  
### <a name="parameters"></a>Параметры  
 `__fstrArg`  
 Адрес объекта `StringReference`, используемый для инициализации текущего объекта `StringReference`.  
  
 `__strArg`  
 Указатель на массив значений char16, используемый для инициализации текущего объекта `StringReference`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на объект типа `StringReference`.  
  
### <a name="remarks"></a>Примечания  
 Поскольку `StringReference` является стандартным классом C++, а не ссылочным классом, он не отображается в **обозревателя объектов**.  
  


## <a name="operator-call"></a>Оператор stringreference:: operator()
Преобразует объект `StringReference` в объект `Platform::String^`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
__declspec(no_release_return) __declspec(no_refcount)  
         operator ::Platform::String^() const  
  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Дескриптор для объекта типа `Platform::String`.  

## <a name="ctor"></a>  Конструктор StringReference::StringReference
Инициализирует новый экземпляр класса `StringReference`.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
    StringReference();  
  
   StringReference(const StringReference& __fstrArg)  
  
StringReference(const ::default::char16* __strArg)  
  
StringReference(const ::default::char16* __strArg, size_t __lenArg)  
```  
  
### <a name="parameters"></a>Параметры  
 `__fstrArg`  
 Объект `StringReference`, данные которого используются для инициализации нового экземпляра.  
  
 `__strArg`  
 Указатель на массив значений char16, используемый для инициализации нового экземпляра.  
  
 `__lenArg`  
 Число элементов в `__strArg`.  
  
### <a name="remarks"></a>Примечания  
 Первая версия этого конструктора является конструктором по умолчанию. Вторая версия инициализирует новый экземпляра класса `StringReference` из объекта, заданного параметром `__fstrArg`. Третья и четвертая перегрузки инициализируют новый `StringReference` экземпляр из массива значений char16. char16 представляет 16-разрядный текстовый символ ЮНИКОДА.  
  


  
## <a name="see-also"></a>См. также  
 [Класс Platform::StringReference](../cppcx/platform-stringreference-class.md)