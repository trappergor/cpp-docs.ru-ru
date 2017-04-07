---
title: "Класс CAtlException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 30c9235f16581c86ab5612522909dc366b1ce17e
ms.lasthandoff: 02/24/2017

---
# <a name="catlexception-class"></a>Класс CAtlException
Этот класс определяет ATL исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CAtlException
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::CAtlException](#catlexception)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::operator HRESULT](#operator_hresult)|Приводит значение HRESULT с текущим объектом.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAtlException::m_hr](#m_hr)|Переменная типа HRESULT, созданный и используется для хранения состояния ошибки.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CAtlException` объект представляет исключительное условие, связанное с операцией ATL. `CAtlException` Класс включает открытого члена данных, содержит код состояния, указывающий причину исключения и оператор приведения, который позволяет обрабатывать исключения, как если бы значение HRESULT.  
  
 Как правило, будет вызывать `AtlThrow` вместо создания `CAtlException` напрямую.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlexcept.h  
  
##  <a name="catlexception"></a>CAtlException::CAtlException  
 Конструктор.  
  
```
CAtlException(HRESULT hr) throw();
CAtlException() throw();
```  
  
### <a name="parameters"></a>Параметры  
 `hr`  
 `HRESULT` Код ошибки.  
  
##  <a name="operator_hresult"></a>CAtlException::operator HRESULT 
 Приводит значение HRESULT с текущим объектом.  
  
```  
operator HRESULT() const throw ();
```  
  
##  <a name="m_hr"></a>CAtlException::m_hr  
 `HRESULT` Элемент данных.  
  
```
HRESULT m_hr;
```  
  
### <a name="remarks"></a>Примечания  
 Член данных, сохраняет условие ошибки. Значение HRESULT задано конструктором, [CAtlException::CAtlException](#catlexception).  
  
## <a name="see-also"></a>См. также  
 [AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

