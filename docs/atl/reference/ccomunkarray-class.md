---
title: Класс CComUnkArray | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComUnkArray
- ATLCOM/ATL::CComUnkArray
- ATLCOM/ATL::CComUnkArray::CComUnkArray
- ATLCOM/ATL::CComUnkArray::Add
- ATLCOM/ATL::CComUnkArray::begin
- ATLCOM/ATL::CComUnkArray::end
- ATLCOM/ATL::CComUnkArray::GetCookie
- ATLCOM/ATL::CComUnkArray::GetUnknown
- ATLCOM/ATL::CComUnkArray::Remove
dev_langs:
- C++
helpviewer_keywords:
- connection points [C++], managing
- CComUnkArray class
ms.assetid: 5fd4b378-a7b5-4cc1-8866-8ab72a73639e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 90622638c2cf26c8d34ec9b584611f91bc1836f4
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37883987"
---
# <a name="ccomunkarray-class"></a>Класс CComUnkArray
В этом классе хранится `IUnknown` указатели и предназначен для использования в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класс шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Параметры  
 *nMaxSize*  
 Максимальное число `IUnknown` указатели, которые могут храниться в статического массива.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|Вызовите этот метод для добавления `IUnknown` указатель на массив.|  
|[CComUnkArray::begin](#begin)|Возвращает указатель на первый `IUnknown` указатель в коллекции.|  
|[CComUnkArray::end](#end)|Возвращает указатель на позицию, следующую за последней `IUnknown` указатель в коллекции.|  
|[CComUnkArray::GetCookie](#getcookie)|Вызовите этот метод, чтобы получить файл cookie, связанный с данной `IUnknown` указатель.|  
|[CComUnkArray::GetUnknown](#getunknown)|Вызовите этот метод для получения `IUnknown` указатель, связанный с заданным файлом cookie.|  
|[CComUnkArray::Remove](#remove)|Вызовите этот метод для удаления `IUnknown` указатель из массива.|  
  
## <a name="remarks"></a>Примечания  
 `CComUnkArray` содержит фиксированное количество `IUnknown` указатели, каждая точка интерфейс для подключения. `CComUnkArray` может использоваться в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класс шаблона. `CComUnkArray<1>` является специализацией шаблона `CComUnkArray` , была оптимизирована для одной точке подключения.  
  
 `CComUnkArray` Методы [начать](#begin) и [окончания](#end) может использоваться для циклического прохождения через все точки подключения (например, когда происходит событие).  
  
 См. в разделе [Добавление точек подключения к объекту](../../atl/adding-connection-points-to-an-object.md) Дополнительные сведения об автоматизации создания подключения укажите учетные записи-посредники.  
  
> [!NOTE]
> **Примечание** класса [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) используется **Добавление класса** мастер при создании элемента управления, который содержит точки подключения. Если вы хотите указать количество точек подключения вручную, измените ссылку с `CComDynamicUnkArray` для `CComUnkArray<` *n* `>`, где *n* — это число точек подключения Обязательно.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="add"></a>  CComUnkArray::Add  
 Вызовите этот метод для добавления `IUnknown` указатель на массив.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 Вызовите этот метод для добавления `IUnknown` указатель на массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанный с вновь добавленный указателя, или 0, если массив не является достаточно большим, чтобы содержать новый указатель.  
  
##  <a name="begin"></a>  CComUnkArray::begin  
 Возвращает указатель на начало коллекции `IUnknown` указателей на интерфейс.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IUnknown` указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Коллекция содержит указатели на интерфейсы, которые хранятся локально в виде `IUnknown`. Вы приводите каждый `IUnknown` интерфейса в тип real интерфейса и затем вызывать ее. Необходимо сначала запрашивать интерфейс.  
  
 Перед использованием `IUnknown` интерфейса, следует проверить, что он не равен NULL.  
  
##  <a name="ccomunkarray"></a>  CComUnkArray::CComUnkArray  
 Конструктор.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Задает коллекцию для хранения `nMaxSize` `IUnknown` указатели и инициализирует указатели NULL.  
  
##  <a name="end"></a>  CComUnkArray::end  
 Возвращает указатель на позицию, следующую за последней `IUnknown` указатель в коллекции.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на `IUnknown` указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 `CComUnkArray` Методы `begin` и `end` может использоваться для циклического прохождения через все точки подключения, например, когда происходит событие.  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>  CComUnkArray::GetCookie  
 Вызовите этот метод, чтобы получить файл cookie, связанный с данной `IUnknown` указатель.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Параметры  
 *ppFind*  
 `IUnknown` Указатель, для которого необходим соответствующий файл cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанный с `IUnknown` указателя, или 0, если нет соответствующего `IUnknown` находится указатель.  
  
### <a name="remarks"></a>Примечания  
 Если имеется несколько экземпляров одной и той же `IUnknown` указателем, эта функция возвращает файл cookie для первого из них.  
  
##  <a name="getunknown"></a>  CComUnkArray::GetUnknown  
 Вызовите этот метод для получения `IUnknown` указатель, связанный с заданным файлом cookie.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 *dwCookie*  
 Файл cookie, для которого связанного `IUnknown` указатель является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает `IUnknown` указателя, или значение NULL, если нет соответствующий файл cookie найден.  
  
##  <a name="remove"></a>  CComUnkArray::Remove  
 Вызовите этот метод для удаления `IUnknown` указатель из массива.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 *dwCookie*  
 Ссылка на файл cookie `IUnknown` указатель, который необходимо удалить из массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если указатель удален, и FALSE в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
