---
title: Класс CHandle | Документация Майкрософт
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
ms.openlocfilehash: cd962e32f423baba6cfabb90f1d9f7fa5d69e170
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37880236"
---
# <a name="chandle-class"></a>Класс CHandle
Этот класс предоставляет методы для создания и использования объекта дескриптора.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CHandle
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Конструктор.|  
|[CHandle:: ~ CHandle](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Вызовите этот метод для присоединения `CHandle` объект для существующего дескриптора.|  
|[CHandle::Close](#close)|Вызовите этот метод, чтобы закрыть `CHandle` объекта.|  
|[CHandle::Detach](#detach)|Вызовите этот метод для отсоединения дескриптора из `CHandle` объекта.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHandle::operator ДЕСКРИПТОР](#operator_handle)|Возвращает значение хранимых дескриптора.|  
|[CHandle::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|Переменную-член, сохраняет дескриптор.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CHandle` объект можно использовать всякий раз, когда дескриптор является обязательным: основное различие заключается в, `CHandle` объект будет автоматически удален.  
  
> [!NOTE]
>  Некоторые функции API будет используйте NULL в качестве пустой или недопустимый дескриптор, а другие — в значение INVALID_HANDLE_VALUE. `CHandle` использует только значение NULL, а также будет считать значение INVALID_HANDLE_VALUE реальных дескриптор. Если вызвать API, которая может вернуть значение INVALID_HANDLE_VALUE, необходимо проверить это значение перед вызовом [CHandle::Attach](#attach) или передается командлету `CHandle` конструктор и вместо этого передайте значение NULL.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>  CHandle::Attach  
 Вызовите этот метод для присоединения `CHandle` объект для существующего дескриптора.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 `CHandle` будет стать владельцем дескриптора *h*.  
  
### <a name="remarks"></a>Примечания  
 Назначает `CHandle` объект *h* обработки. В сборках отлаживает ATLASSERT будет вызвано, если *h* имеет значение NULL. Проверка других допустимость дескриптора не проводится.  
  
##  <a name="chandle"></a>  CHandle::CHandle  
 Конструктор.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 Дескриптор существующей или `CHandle`.  
  
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
 Вызовите этот метод, чтобы закрыть `CHandle` объекта.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Закрывает дескриптор open объекта. Если дескриптор имеет значение NULL, который будет в том случае, если `Close` уже был вызван, ATLASSERT возникает в отладочных сборках.  
  
##  <a name="detach"></a>  CHandle::Detach  
 Вызовите этот метод для отсоединения дескриптора из `CHandle` объекта.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает дескриптор отключается.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение дескриптор.  
  
##  <a name="m_h"></a>  CHandle::m_h  
 Переменную-член, сохраняет дескриптор.  
  
```
HANDLE m_h;
```  
  
##  <a name="operator_eq"></a>  CHandle::operator =  
 Оператор присваивания.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Параметры  
 *h*  
 `CHandle` будет стать владельцем дескриптора *h*.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на новый `CHandle` объекта.  
  
### <a name="remarks"></a>Примечания  
 Если `CHandle` объект в настоящее время содержит дескриптор, он будет закрыт. `CHandle` Объекта, передаваемого будет иметь его дескриптор ссылки, присваивается значение NULL. Это гарантирует, что два `CHandle` объектов никогда не будет содержать том же дескрипторе active.  
  
##  <a name="operator_handle"></a>  CHandle::operator ДЕСКРИПТОР  
 Возвращает значение хранимых дескриптора.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает значение, хранящееся в [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
