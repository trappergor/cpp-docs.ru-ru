---
title: "Класс CComDynamicUnkArray | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::CComDynamicUnkArray
- ATLCOM/ATL::CComDynamicUnkArray::Add
- ATLCOM/ATL::CComDynamicUnkArray::begin
- ATLCOM/ATL::CComDynamicUnkArray::clear
- ATLCOM/ATL::CComDynamicUnkArray::end
- ATLCOM/ATL::CComDynamicUnkArray::GetAt
- ATLCOM/ATL::CComDynamicUnkArray::GetCookie
- ATLCOM/ATL::CComDynamicUnkArray::GetSize
- ATLCOM/ATL::CComDynamicUnkArray::GetUnknown
- ATLCOM/ATL::CComDynamicUnkArray::Remove
dev_langs: C++
helpviewer_keywords:
- connection points [C++], managing
- CComDynamicUnkArray class
ms.assetid: 202470d7-9a1b-498f-b96d-659d681acd65
caps.latest.revision: "17"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 5863c224ed47c70ce485bde3cd693c29afbfbc04
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="ccomdynamicunkarray-class"></a>Класс CComDynamicUnkArray
Этот класс содержит массив **IUnknown** указатели.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CComDynamicUnkArray
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComDynamicUnkArray::CComDynamicUnkArray](#ccomdynamicunkarray)|Конструктор. Инициализирует значений в коллекции **NULL** и размера коллекции равным нулю.|  
|[CComDynamicUnkArray:: ~ CComDynamicUnkArray](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CComDynamicUnkArray::Add](#add)|Вызовите этот метод для добавления `IUnknown` указатель на массив.|  
|[CComDynamicUnkArray::begin](#begin)|Возвращает указатель на первый `IUnknown` указатель в коллекции.|  
|[CComDynamicUnkArray::clear](#clear)|Очищает массива.|  
|[CComDynamicUnkArray::end](#end)|Возвращает указатель на элемент, следующий за последние **IUnknown** указатель в коллекции.|  
|[CComDynamicUnkArray::GetAt](#getat)|Извлекает элемент по указанному индексу.|  
|[CComDynamicUnkArray::GetCookie](#getcookie)|Этот метод вызывается для получения файлов cookie, связанные с данной **IUnknown** указателя.|  
|[CComDynamicUnkArray::GetSize](#getsize)|Возвращает длину массива.|  
|[CComDynamicUnkArray::GetUnknown](#getunknown)|Этот метод вызывается для получения **IUnknown** указатель, связанный с данной куки-файл.|  
|[CComDynamicUnkArray::Remove](#remove)|Этот метод вызывается для удаления **IUnknown** указателя из массива.|  
  
## <a name="remarks"></a>Примечания  
 **CComDynamicUnkArray** содержит динамически выделяемого массива из **IUnknown** указателей, каждый интерфейс для подключения точки. **CComDynamicUnkArray** можно использовать в качестве параметра [IConnectionPointImpl](../../atl/reference/iconnectionpointimpl-class.md) класса шаблона.  
  
 **CComDynamicUnkArray** методы [начать](#begin) и [окончания](#end) можно использовать для перебора всех точек соединения (например, когда происходит событие).  
  
 В разделе [Добавление подключения указывает на объект](../../atl/adding-connection-points-to-an-object.md) подробные сведения об автоматизации создания соединения привязка прокси-серверов.  
  
> [!NOTE]
> **Примечание** класса **CComDynamicUnkArray** используется **добавить класс** мастер при создании элемента управления, который имеет точек подключения. Если вы хотите указать количество точек подключения вручную, измените ссылку с **CComDynamicUnkArray** для `CComUnkArray<`  *n*  `>`, где  *n*  число необходимых точки подключения.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcom.h  
  
##  <a name="add"></a>CComDynamicUnkArray::Add  
 Вызовите этот метод для добавления **IUnknown** указатель на массив.  
  
```
DWORD Add(IUnknown* pUnk);
```  
  
### <a name="parameters"></a>Параметры  
 *pUnk*  
 **IUnknown** указатель, чтобы добавить в массив.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает куки-файл, связанный с вновь добавленный указателя.  
  
##  <a name="begin"></a>CComDynamicUnkArray::begin  
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
  
##  <a name="clear"></a>CComDynamicUnkArray::clear  
 Очищает массива.  
  
```
void clear();
```  
  
##  <a name="ccomdynamicunkarray"></a>CComDynamicUnkArray::CComDynamicUnkArray  
 Конструктор.  
  
```
CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Задает размер коллекции нулю и инициализирует значения для **NULL**. Деструктор освобождает коллекции, но при необходимости.  
  
##  <a name="dtor"></a>CComDynamicUnkArray:: ~ CComDynamicUnkArray  
 Деструктор  
  
```
~CComDynamicUnkArray();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает ресурсы, выделенные конструктором класса.  
  
##  <a name="end"></a>CComDynamicUnkArray::end  
 Возвращает указатель на элемент, следующий за последние **IUnknown** указатель в коллекции.  
  
```
IUnknown**
    end();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на **IUnknown** указатель на интерфейс.  
  
##  <a name="getat"></a>CComDynamicUnkArray::GetAt  
 Извлекает элемент по указанному индексу.  
  
```
IUnknown* GetAt(int nIndex);
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Индекс извлекаемого элемента.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [IUnknown](http://msdn.microsoft.com/library/windows/desktop/ms680509) интерфейса.  
  
##  <a name="getcookie"></a>CComDynamicUnkArray::GetCookie  
 Этот метод вызывается для получения файлов cookie, связанные с данной **IUnknown** указателя.  
  
```
DWORD WINAPI GetCookie(IUnknown** ppFind);
```  
  
### <a name="parameters"></a>Параметры  
 `ppFind`  
 **IUnknown** указатель, для которого необходим соответствующий файл cookie.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie, связанные с **IUnknown** указателя, или нуль, если совпадений **IUnknown** находится указатель.  
  
### <a name="remarks"></a>Примечания  
 Если имеется несколько экземпляров одной и той же **IUnknown** указателем, эта функция возвращает куки-файл для первого.  
  
##  <a name="getsize"></a>CComDynamicUnkArray::GetSize  
 Возвращает длину массива.  
  
```
int GetSize() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Длина массива.  
  
##  <a name="getunknown"></a>CComDynamicUnkArray::GetUnknown  
 Этот метод вызывается для получения **IUnknown** указатель, связанный с данной куки-файл.  
  
```
IUnknown* WINAPI GetUnknown(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Файл cookie, для которого связанный **IUnknown** указатель является обязательным.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает **IUnknown** указатель или значение NULL, если соответствующие объекты cookie не найден.  
  
##  <a name="remove"></a>CComDynamicUnkArray::Remove  
 Этот метод вызывается для удаления **IUnknown** указателя из массива.  
  
```
BOOL Remove(DWORD dwCookie);
```  
  
### <a name="parameters"></a>Параметры  
 `dwCookie`  
 Создание ссылок на файл cookie **IUnknown** указатель, который необходимо удалить из массива.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение TRUE, если указатель был удален. в противном случае — значение FALSE.  
  
## <a name="see-also"></a>См. также  
 [Класс CComUnkArray](../../atl/reference/ccomunkarray-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
