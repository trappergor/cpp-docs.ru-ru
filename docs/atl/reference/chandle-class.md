---
title: "Класс CHandle | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 19
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: bbc0703ae5eaab01c0819be7e378509c7dc579ef
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="chandle-class"></a>Класс CHandle
Этот класс предоставляет методы для создания и использования объекта дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CHandle
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Конструктор.|  
|[CHandle:: ~ CHandle](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Этот метод вызывается для присоединения `CHandle` объекта для существующего дескриптора.|  
|[CHandle::Close](#close)|Вызовите этот метод, чтобы закрыть `CHandle` объекта.|  
|[CHandle::Detach](#detach)|Этот метод вызывается для отсоединения дескриптор из `CHandle` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::operator ДЕСКРИПТОРА](#operator_handle)|Возвращает значение хранимого дескриптора.|  
|[CHandle::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Член переменной для хранения дескриптора.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CHandle` объект можно использовать всякий раз, когда требуется маркер: основное различие заключается в, `CHandle` объекта будет автоматически удалено.  
  
> [!NOTE]
>  Некоторые функции API будет использоваться как дескриптор пустое или недопустимое значение NULL, другие используют INVALID_HANDLE_VALUE. `CHandle`использует только значение NULL, а также будет считать INVALID_HANDLE_VALUE реального дескриптора. При вызове API, который может возвращать INVALID_HANDLE_VALUE необходимо проверить наличие это значение перед вызовом метода [CHandle::Attach](#attach) или передав его `CHandle` конструктор и вместо этого передайте значение NULL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>CHandle::Attach  
 Этот метод вызывается для присоединения `CHandle` объекта для существующего дескриптора.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 `CHandle`будет распоряжаться дескриптор `h`.  
  
### <a name="remarks"></a>Примечания  
 Назначает `CHandle` объект `h` обработки. В сборках отлаживает ATLASSERT будет создано, если `h` имеет значение NULL. Проверка других относительно достоверности дескриптор не выполняется.  
  
##  <a name="chandle"></a>CHandle::CHandle  
 Конструктор.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 Дескриптор существующей или `CHandle`.  
  
### <a name="remarks"></a>Примечания  
 Создает новый `CHandle` объекта, при необходимости с помощью существующего дескриптора или `CHandle` объекта.  
  
##  <a name="dtor"></a>CHandle:: ~ CHandle  
 Деструктор  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает `CHandle` путем вызова метода [CHandle::Close](#close).  
  
##  <a name="close"></a>CHandle::Close  
 Вызовите этот метод, чтобы закрыть `CHandle` объекта.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает дескриптор открытого объекта. Если дескриптор имеет значение NULL, который будет в том случае, если **закрыть** уже был вызван, ATLASSERT, будет создано в отладочных построениях.  
  
##  <a name="detach"></a>CHandle::Detach  
 Этот метод вызывается для отсоединения дескриптор из `CHandle` объекта.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор отсоединения.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение дескриптора.  
  
##  <a name="m_h"></a>CHandle::m_h  
 Член переменной для хранения дескриптора.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>CHandle::operator =  
 Оператор присваивания.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `h`  
 `CHandle`будет распоряжаться дескриптор `h`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на новый `CHandle` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CHandle` объект в настоящее время содержит дескриптор, оно будет закрыто. `CHandle` Объекта, передаваемого будет его дескриптор ссылки, присваивается значение NULL. Это гарантирует, что два `CHandle` объектов никогда не будет содержать тот же дескриптор active.  
  
##  <a name="operator_handle"></a>CHandle::operator ДЕСКРИПТОРА  
 Возвращает значение хранимого дескриптора.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает значение, хранящееся в [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

