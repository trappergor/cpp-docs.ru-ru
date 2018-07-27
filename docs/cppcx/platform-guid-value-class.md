---
title: Класс значения Platform::GUID | Документы Microsoft
ms.custom: ''
ms.date: 12/30/2016
ms.technology: cpp-windows
ms.topic: reference
f1_keywords:
- VCCORLIB/Platform::Guid
dev_langs:
- C++
helpviewer_keywords:
- Platform::Guid Struct
ms.assetid: 25c0bfb2-7f93-44d8-bdf4-ef4fbac3424a
author: ghogen
ms.author: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c295138d6239ce516b4f322fb5fc479e2235a6be
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33089455"
---
# <a name="platformguid-value-class"></a>Класс значения Platform::Guid
Представляет тип [GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx) в системе типов среды выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```cpp  
public value struct Guid  
```  
  
### <a name="members"></a>Члены  
 Структура Guid имеет методы Equals(), GetHashCode() и ToString(), производные от [Platform::Object Class](../cppcx/platform-object-class.md), и метод GetTypeCode(), производный от [Platform::Type Class](../cppcx/platform-type-class.md). У структуры Guid также имеются следующие члены.  
  
|Член|Описание|  
|------------|-----------------|  
|[Guid](#ctor)|Инициализирует новый экземпляр структуры Guid.|  
|[operator==](#operator-equality)|Оператор равенства.|  
|[operator!=](#operator-not-equal)|Оператор неравенства.|  
|[operator()](#operator-call)|Преобразует Guid в GUID.|  
  
### <a name="remarks"></a>Примечания  
 Пример создания новой структуры Platform::Guid с использованием функции Windows [CoCreateGuid](http://msdn.microsoft.com/library/windows/desktop/ms688568\(v=vs.85\).aspx)см. в разделе [Компонент WinRT: как создать GUID?](http://blogs.msdn.com/b/eternalcoding/archive/2013/03/25/winrt-component-how-to-generate-a-guid.aspx)  
  
### <a name="requirements"></a>Требования  
 **Минимальный поддерживаемый клиент:** Windows 8  
  
 **Минимальный поддерживаемый сервер:** Windows Server 2012  
  
 **Пространство имен:** Platform  
  
 **Метаданные:** platform.winmd  

 
## <a name="ctor"></a> Конструкторы GUID::GUID
Инициализирует новый экземпляр структуры Guid.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        unsigned char d,   
        unsigned char e,   
        unsigned char f,   
        unsigned char g,   
        unsigned char h,   
        unsigned char i,   
        unsigned char j,   
        unsigned char k  );  
  
    Guid(GUID m);  
  
    Guid(  
        unsigned int a,   
        unsigned short b,   
        unsigned short c,   
        Array<unsigned char>^ n );  
```  
  
### <a name="parameters"></a>Параметры  
 `a`  
 Первые 4 байта GUID.  
  
 `b`  
 Следующие 2 байта GUID.  
  
 `c`  
 Следующие 2 байта GUID.  
  
 `d`  
 Следующий байт GUID.  
  
 `e`  
 Следующий байт GUID.  
  
 `f`  
 Следующий байт GUID.  
  
 `g`  
 Следующий байт GUID.  
  
 `h`  
 Следующий байт GUID.  
  
 `i`  
 Следующий байт GUID.  
  
 `j`  
 Следующий байт GUID.  
  
 `k`  
 Следующий байт GUID.  
  
 `m`  
 GUID согласно определению.  
  
 `n`  
 Оставшиеся 8 байтов GUID.  
  

## <a name="operator-equality"></a> GUID::operator ==-оператор
Сравнивает два кода GUID.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::Guid::operator==  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение true, если GUID равны.

## <a name="operator-inequality"></a> GUID::operator! =-оператор
Сравнивает два кода GUID.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::Guid::operator!=  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение true, если два кода GUID не равны.



## <a name="operator-call"></a> Оператор GUID:: operator()
Неявно преобразует [структуры GUID](http://msdn.microsoft.com/library/windows/desktop/aa373931\(v=vs.85\).aspx)в Platform::guid.  
  
### <a name="syntax"></a>Синтаксис  
  
```cpp  
Platform::Guid operator()  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Структура Guid.  
  
  
## <a name="see-also"></a>См. также  
 [Пространство имен Platform](../cppcx/platform-namespace-c-cx.md)