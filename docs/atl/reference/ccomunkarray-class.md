---
title: "Класс CComUnkArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComUnkArray
- ATL.CComUnkArray<nMaxSize>
- ATL::CComUnkArray<nMaxSize>
- ATL::CComUnkArray
- CComUnkArray
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 94f1062ff3808f527874a8890eca95c9b655b1bf
ms.lasthandoff: 02/24/2017

---
# <a name="ccomunkarray-class"></a>Класс CComUnkArray
В этом классе хранится **IUnknown** указатели и предназначен для использования в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Параметры  
 *nMaxSize*  
 Максимальное число **IUnknown** указатели, которые могут храниться в статического массива.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|Вызовите этот метод, чтобы добавить **IUnknown** указатель на массив.|  
|[CComUnkArray::begin](#begin)|Возвращает указатель на первый **IUnknown** указатель в коллекции.|  
|[CComUnkArray::end](#end)|Возвращает указатель на позицию сразу за последней **IUnknown** указатель в коллекции.|  
|[CComUnkArray::GetCookie](#getcookie)|Этот метод вызывается для получения файла cookie, связанного с данной **IUnknown** указателя.|  
|[CComUnkArray::GetUnknown](#getunknown)|Этот метод вызывается для получения **IUnknown** указатель, связанный с данной cookie.|  
|[CComUnkArray::Remove](#remove)|Этот метод вызывается для удаления **IUnknown** указатель из массива.|  
  
## <a name="remarks"></a>Примечания  
 **CComUnkArray** содержит фиксированное число **IUnknown** указатели, каждая точка интерфейс для подключения. **CComUnkArray** может использоваться в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона. **CComUnkArray\<1 настроек** является специализацией шаблона **CComUnkArray** , была оптимизирована для одной точке соединения.  
  
 **CComUnkArray** методы [начать](#begin) и [end](#end) может использоваться для перебора всех точек подключения (например, когда происходит событие).  
  
 В разделе [Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md) подробные сведения об автоматизации создания соединения точки прокси.  
  
> [!NOTE]
> **Примечание** класса [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) используется **добавить класс** мастер при создании элемента управления, имеющий точки подключения. Если требуется вручную указать количество точек подключения, измените ссылки из **CComDynamicUnkArray** для `CComUnkArray<` *n* `>`, где *n* число необходимых точек подключения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcom.h  
  
##  <a name="a-nameadda--ccomunkarrayadd"></a><a name="add"></a>CComUnkArray::Add  
 Вызовите этот метод, чтобы добавить **IUnknown** указатель на массив.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 Вызовите этот метод, чтобы добавить **IUnknown** указатель на массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает куки-файл, связанный с вновь добавленный указателя, или 0, если массив не является достаточно велик, чтобы вместить новый указатель.  
  
##  <a name="a-namebegina--ccomunkarraybegin"></a><a name="begin"></a>CComUnkArray::begin  
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
  
##  <a name="a-nameccomunkarraya--ccomunkarrayccomunkarray"></a><a name="ccomunkarray"></a>CComUnkArray::CComUnkArray  
 Конструктор.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Задает коллекцию для хранения `nMaxSize` **IUnknown** указатели и инициализирует указатели **NULL**.  
  
##  <a name="a-nameenda--ccomunkarrayend"></a><a name="end"></a>CComUnkArray::end  
 Возвращает указатель на позицию сразу за последней **IUnknown** указатель в коллекции.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 `CComUnkArray` Методы **начать** и **end** можно перебрать все точки подключения, например, когда происходит событие.  
  
 [!code-cpp[NVC_ATL_COM&#44;](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="a-namegetcookiea--ccomunkarraygetcookie"></a><a name="getcookie"></a>CComUnkArray::GetCookie  
 Этот метод вызывается для получения файла cookie, связанного с данной **IUnknown** указателя.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFind`  
 **IUnknown** указатель, для которого необходим соответствующий файл cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанные с **IUnknown** указателя, или 0, если нет соответствующего **IUnknown** находится указатель.  
  
### <a name="remarks"></a>Примечания  
 Если имеется несколько экземпляров одной и той же **IUnknown** указатель, эта функция возвращает файл cookie для первого из них.  
  
##  <a name="a-namegetunknowna--ccomunkarraygetunknown"></a><a name="getunknown"></a>CComUnkArray::GetUnknown  
 Этот метод вызывается для получения **IUnknown** указатель, связанный с данной cookie.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Файл cookie, для которого связанный **IUnknown** указатель является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **IUnknown** указатель или значение NULL, если соответствующие объекты cookie не найден.  
  
##  <a name="a-nameremovea--ccomunkarrayremove"></a><a name="remove"></a>CComUnkArray::Remove  
 Этот метод вызывается для удаления **IUnknown** указатель из массива.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Ссылка на файл cookie **IUnknown** указатель, удаляемый из массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при удалении указателя **FALSE** в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

