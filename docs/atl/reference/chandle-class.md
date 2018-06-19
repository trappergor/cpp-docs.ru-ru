---
title: Класс CHandle | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CHandle
- ATLBASE/ATL::CHandle
- ATLBASE/ATL::CHandle::CHandle
- ATLBASE/ATL::CHandle::Attach
- ATLBASE/ATL::CHandle::Close
- ATLBASE/ATL::CHandle::Detach
- ATLBASE/ATL::CHandle::m_h
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: b57aab927380f8801c3b9cab258a695c7d8a59d0
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363075"
---
# <a name="chandle-class"></a>Класс CHandle
Этот класс предоставляет методы для создания и использования объекта дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CHandle
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Конструктор.|  
|[CHandle:: ~ CHandle](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Этот метод вызывается для присоединения `CHandle` объект для существующего дескриптора.|  
|[CHandle::Close](#close)|Вызовите этот метод для закрытия `CHandle` объекта.|  
|[CHandle::Detach](#detach)|Этот метод вызывается для отсоединения дескриптора от `CHandle` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::operator ДЕСКРИПТОРА](#operator_handle)|Возвращает значение хранимого дескриптора.|  
|[CHandle::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Переменной-члена, сохранение дескриптора.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CHandle` объект можно использовать всякий раз, когда требуется маркер: основное отличие заключается в, `CHandle` объект будет автоматически удален.  
  
> [!NOTE]
>  Некоторые функции API будет использовать как дескриптор пустое или недопустимое значение NULL, другие используют INVALID_HANDLE_VALUE. `CHandle` используются только значение NULL, а также будет считать INVALID_HANDLE_VALUE реальные дескриптор. При вызове API, которая может вернуть INVALID_HANDLE_VALUE необходимо проверить это значение перед вызовом [CHandle::Attach](#attach) или передать его `CHandle` конструктор и вместо этого передать значение NULL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>  CHandle::Attach  
 Этот метод вызывается для присоединения `CHandle` объект для существующего дескриптора.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 `CHandle` будет распоряжаться дескриптор `h`.  
  
### <a name="remarks"></a>Примечания  
 Назначает `CHandle` объект `h` обработки. В сборках отлаживает ATLASSERT возникает если `h` имеет значение NULL. Проверка других допустимость дескриптора не проводится.  
  
##  <a name="chandle"></a>  CHandle::CHandle  
 Конструктор.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 Существующего дескриптора или `CHandle`.  
  
### <a name="remarks"></a>Примечания  
 Создает новый `CHandle` объекта, при необходимости с помощью существующего дескриптора или `CHandle` объекта.  
  
##  <a name="dtor"></a>  CHandle:: ~ CHandle  
 Деструктор  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает `CHandle` путем вызова метода [CHandle::Close](#close).  
  
##  <a name="close"></a>  CHandle::Close  
 Вызовите этот метод для закрытия `CHandle` объекта.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает дескриптор открытого объекта. Если маркер имеет значение NULL, которое будет в том случае, если **закрыть** уже был вызван, ATLASSERT будет вызываться в отладочных построениях.  
  
##  <a name="detach"></a>  CHandle::Detach  
 Этот метод вызывается для отсоединения дескриптора от `CHandle` объекта.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор отключаемой.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение дескриптора.  
  
##  <a name="m_h"></a>  CHandle::m_h  
 Переменной-члена, сохранение дескриптора.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>  CHandle::operator =  
 Оператор присваивания.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 `CHandle` будет распоряжаться дескриптор `h`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на новый `CHandle` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CHandle` объект в настоящее время содержит дескриптор, оно будет закрыто. `CHandle` Объектов, передаваемых в будет иметь свою ссылку дескриптор, присваивается значение NULL. Это гарантирует, что два `CHandle` объектов никогда не будет содержать тот же дескриптор active.  
  
##  <a name="operator_handle"></a>  CHandle::operator ДЕСКРИПТОРА  
 Возвращает значение хранимого дескриптора.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает значение, хранящееся в [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
