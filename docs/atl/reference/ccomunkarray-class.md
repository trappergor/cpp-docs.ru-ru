---
title: Класс CComUnkArray | Документы Microsoft
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
ms.openlocfilehash: 0de49180052a6fdb7bde32274e032ea1dd9bfb87
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
---
# <a name="ccomunkarray-class"></a>Класс CComUnkArray
Этот класс хранит **IUnknown** указателей и предназначен для использования в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<unsigned int nMaxSize>
class CComUnkArray
```  
  
#### <a name="parameters"></a>Параметры  
 *nMaxSize*  
 Максимальное число **IUnknown** указателей, которое может содержаться в статического массива.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComUnkArray::CComUnkArray](#ccomunkarray)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComUnkArray::Add](#add)|Вызовите этот метод для добавления **IUnknown** указатель на массив.|  
|[CComUnkArray::begin](#begin)|Возвращает указатель на первый **IUnknown** указатель в коллекции.|  
|[CComUnkArray::end](#end)|Возвращает указатель на элемент, следующий за последние **IUnknown** указатель в коллекции.|  
|[CComUnkArray::GetCookie](#getcookie)|Этот метод вызывается для получения файлов cookie, связанные с данной **IUnknown** указателя.|  
|[CComUnkArray::GetUnknown](#getunknown)|Этот метод вызывается для получения **IUnknown** указатель, связанный с данной куки-файл.|  
|[CComUnkArray::Remove](#remove)|Этот метод вызывается для удаления **IUnknown** указателя из массива.|  
  
## <a name="remarks"></a>Примечания  
 **CComUnkArray** содержит фиксированное число **IUnknown** указателей, каждый интерфейс для подключения точки. **CComUnkArray** можно использовать в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона. **CComUnkArray\<1 >** является специализацией шаблона **CComUnkArray** , была оптимизирована для одной точке соединения.  
  
 **CComUnkArray** методы [начать](#begin) и [окончания](#end) можно использовать для перебора всех точек соединения (например, когда происходит событие).  
  
 В разделе [Добавление подключения указывает на объект](../../atl/adding-connection-points-to-an-object.md) подробные сведения об автоматизации создания соединения привязка прокси-серверов.  
  
> [!NOTE]
> **Примечание** класса [CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md) используется **добавить класс** мастер при создании элемента управления, который имеет точек подключения. Если вы хотите указать количество точек подключения вручную, измените ссылку с **CComDynamicUnkArray** для `CComUnkArray<` *n* `>`, где *n*число необходимых точки подключения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="add"></a>  CComUnkArray::Add  
 Вызовите этот метод для добавления **IUnknown** указатель на массив.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 Вызовите этот метод для добавления **IUnknown** указатель на массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает куки-файл, связанный с вновь добавленный указателя, или 0, если массив не является достаточно велик, чтобы вместить новый указатель.  
  
##  <a name="begin"></a>  CComUnkArray::begin  
 Возвращает указатель на начало коллекции **IUnknown** указателей на интерфейс.  
  
```
IUnknown**
    begin();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 Коллекция содержит указатели на интерфейсы, которые хранятся локально в виде **IUnknown**. Приведение каждого **IUnknown** интерфейса в тип real интерфейса и затем вызывать ее. Необходимо запросить интерфейс.  
  
 Перед использованием **IUnknown** интерфейс, должна проверять, что он не **NULL**.  
  
##  <a name="ccomunkarray"></a>  CComUnkArray::CComUnkArray  
 Конструктор.  
  
```
CComUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Задает коллекцию для хранения `nMaxSize` **IUnknown** указателей и инициализирует указатели на **NULL**.  
  
##  <a name="end"></a>  CComUnkArray::end  
 Возвращает указатель на элемент, следующий за последние **IUnknown** указатель в коллекции.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
### <a name="remarks"></a>Примечания  
 `CComUnkArray` Методы **начать** и **окончания** можно использовать для перебора всех точек подключения, например, когда происходит событие.  
  
 [!code-cpp[NVC_ATL_COM#44](../../atl/codesnippet/cpp/ccomunkarray-class_1.cpp)]  
  
##  <a name="getcookie"></a>  CComUnkArray::GetCookie  
 Этот метод вызывается для получения файлов cookie, связанные с данной **IUnknown** указателя.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFind`  
 **IUnknown** указатель, для которого необходим соответствующий файл cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанные с **IUnknown** указателя, или 0, если нет соответствующего **IUnknown** находится указатель.  
  
### <a name="remarks"></a>Примечания  
 Если имеется несколько экземпляров одной и той же **IUnknown** указателем, эта функция возвращает куки-файл для первого.  
  
##  <a name="getunknown"></a>  CComUnkArray::GetUnknown  
 Этот метод вызывается для получения **IUnknown** указатель, связанный с данной куки-файл.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Файл cookie, для которого связанный **IUnknown** указатель является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **IUnknown** указатель или значение NULL, если соответствующие объекты cookie не найден.  
  
##  <a name="remove"></a>  CComUnkArray::Remove  
 Этот метод вызывается для удаления **IUnknown** указателя из массива.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Создание ссылок на файл cookie **IUnknown** указатель, который необходимо удалить из массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **TRUE** при удалении указатель **FALSE** в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CComDynamicUnkArray](../../atl/reference/ccomdynamicunkarray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
