---
title: Класс CAtlException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAtlException
- ATLEXCEPT/ATL::CAtlException
- ATLEXCEPT/ATL::CAtlException::CAtlException
- ATLEXCEPT/ATL::CAtlException::m_hr
dev_langs:
- C++
helpviewer_keywords:
- CAtlException class
ms.assetid: 3fd7b041-f70d-4292-b947-0d70781d95a8
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: aaafdf42d218e2c3bca1e8ee28c27898f80bcf40
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32357874"
---
# <a name="catlexception-class"></a>Класс CAtlException
Этот класс определяет ATL исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlException
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|Приводит текущий объект в значение HRESULT.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|Переменная типа HRESULT созданный объект и используется для хранения состояния ошибки.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CAtlException` объект представляет исключительное условие, связанное с операцией ATL. `CAtlException` Класс включает это открытый элемент данных, хранит код состояния, указывающее причину исключения и оператора приведения, позволяющий обрабатывать исключение, как если бы он был HRESULT.  
  
 Как правило, вы будете вызывать `AtlThrow` вместо создания `CAtlException` объекта напрямую.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlexcept.h  
  
##  <a name="catlexception"></a>  CAtlException::CAtlException  
 Конструктор.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hr`  
 `HRESULT` Код ошибки.  
  
##  <a name="operator_hresult"></a>  CAtlException::operator HRESULT 
 Приводит текущий объект в значение HRESULT.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>  CAtlException::m_hr  
 `HRESULT` Элемент данных.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Примечания  
 Элемент данных сохраняет ошибки. Значение HRESULT задано с помощью конструктора [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>См. также  
 [AtlThrow](debugging-and-error-reporting-global-functions.md#atlthrow)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
