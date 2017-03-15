---
title: "Класс CComDynamicUnkArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComDynamicUnkArray
- CComDynamicUnkArray
- ATL::CComDynamicUnkArray
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 69fc2c9dbb86f88c85461e765182fd88050521e9
ms.lasthandoff: 02/24/2017

---
# <a name="ccomdynamicunkarray-class"></a>Класс CComDynamicUnkArray
Этот класс содержит массив **IUnknown** указатели.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Конструктор. Инициализирует значений в коллекции **NULL** и размер коллекции в ноль.|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|Вызовите этот метод, чтобы добавить `IUnknown` указатель на массив.|  
|[CComDynamicUnkArray::begin](#begin)|Возвращает указатель на первый `IUnknown` указатель в коллекции.|  
|[CComDynamicUnkArray::clear](#clear)|Очищает массив.|  
|[CComDynamicUnkArray::end](#end)|Возвращает указатель на позицию сразу за последней **IUnknown** указатель в коллекции.|  
|[CComDynamicUnkArray::GetAt](#getat)|Извлекает элемент по указанному индексу.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|Этот метод вызывается для получения файла cookie, связанного с данной **IUnknown** указателя.|  
|[CComDynamicUnkArray::GetSize](#getsize)|Возвращает длину массива.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Этот метод вызывается для получения **IUnknown** указатель, связанный с данной cookie.|  
|[CComDynamicUnkArray::Remove](#remove)|Этот метод вызывается для удаления **IUnknown** указатель из массива.|  
  
## <a name="remarks"></a>Примечания  
 **CComDynamicUnkArray** содержит динамически выделяемого массива **IUnknown** указатели, каждая точка интерфейс для подключения. **CComDynamicUnkArray** может использоваться в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона.  
  
 **CComDynamicUnkArray** методы [начать](#begin) и [end](#end) может использоваться для перебора всех точек подключения (например, когда происходит событие).  
  
 В разделе [Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md) подробные сведения об автоматизации создания соединения точки прокси.  
  
> [!NOTE]
> **Примечание** класса **CComDynamicUnkArray** используется **добавить класс** мастер при создании элемента управления, имеющий точки подключения. Если требуется вручную указать количество точек подключения, измените ссылки из **CComDynamicUnkArray** для `CComUnkArray<` *n* `>`, где *n* число необходимых точек подключения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameadda--ccomdynamicunkarrayadd"></a><a name="add"></a>CComDynamicUnkArray::Add  
 Вызовите этот метод, чтобы добавить **IUnknown** указатель на массив.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 **IUnknown** указатель, чтобы добавить в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанные с вновь добавленный указателя.  
  
##  <a name="a-namebegina--ccomdynamicunkarraybegin"></a><a name="begin"></a>CComDynamicUnkArray::begin  
 Возвращает указатель на начало коллекции **IUnknown** указателей на интерфейс.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Коллекция содержит указатели на интерфейсы, которые хранятся локально в виде **IUnknown**. Нужно привести каждого **IUnknown** интерфейс для типа real интерфейса, а затем вызвать через него. Необходимо запрашивать интерфейс.  
  
 Перед использованием **IUnknown** интерфейс, следует проверить, что это не **NULL**.  
  
##  <a name="a-namecleara--ccomdynamicunkarrayclear"></a><a name="clear"></a>CComDynamicUnkArray::clear  
 Очищает массив.  
  
```
void clear();
```  
  
##  <a name="a-nameccomdynamicunkarraya--ccomdynamicunkarrayccomdynamicunkarray"></a><a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 Конструктор.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Задает размер коллекции нулю и инициализирует значения для **NULL**. Деструктор освобождает коллекции, при необходимости.  
  
##  <a name="a-namedtora--ccomdynamicunkarrayccomdynamicunkarray"></a><a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 Деструктор  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает ресурсы, выделенные конструктором класса.  
  
##  <a name="a-nameenda--ccomdynamicunkarrayend"></a><a name="end"></a>CComDynamicUnkArray::end  
 Возвращает указатель на позицию сразу за последней **IUnknown** указатель в коллекции.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
##  <a name="a-namegetata--ccomdynamicunkarraygetat"></a><a name="getat"></a>CComDynamicUnkArray::GetAt  
 Извлекает элемент по указанному индексу.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс извлекаемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейса.  
  
##  <a name="a-namegetcookiea--ccomdynamicunkarraygetcookie"></a><a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 Этот метод вызывается для получения файла cookie, связанного с данной **IUnknown** указателя.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFind`  
 **IUnknown** указатель, для которого необходим соответствующий файл cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанные с **IUnknown** указателя, или нуль, если нет соответствующего **IUnknown** находится указатель.  
  
### <a name="remarks"></a>Примечания  
 Если имеется несколько экземпляров одной и той же **IUnknown** указатель, эта функция возвращает файл cookie для первого из них.  
  
##  <a name="a-namegetsizea--ccomdynamicunkarraygetsize"></a><a name="getsize"></a>CComDynamicUnkArray::GetSize  
 Возвращает длину массива.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина массива.  
  
##  <a name="a-namegetunknowna--ccomdynamicunkarraygetunknown"></a><a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 Этот метод вызывается для получения **IUnknown** указатель, связанный с данной cookie.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Файл cookie, для которого связанный **IUnknown** указатель является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **IUnknown** указатель или значение NULL, если соответствующие объекты cookie не найден.  
  
##  <a name="a-nameremovea--ccomdynamicunkarrayremove"></a><a name="remove"></a>CComDynamicUnkArray::Remove  
 Этот метод вызывается для удаления **IUnknown** указатель из массива.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Ссылка на файл cookie **IUnknown** указатель, удаляемый из массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если указатель был удален. в противном случае — значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Класс CComUnkArray](../../atl/reference/ccomunkarray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

