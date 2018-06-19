---
title: Класс CComQIPtr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr
- ATLCOMCLI/ATL::CComQIPtr::CComQIPtr
dev_langs:
- C++
helpviewer_keywords:
- CComQIPtr class
ms.assetid: 969cacb5-05b6-4af4-b683-24911d70242d
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 66c6cc1484ef84ce53ffaf5529575eea43431869
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359183"
---
# <a name="ccomqiptr-class"></a>Класс CComQIPtr
Класс интеллектуальный указатель для управления указателей интерфейса СОМ.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 COM-интерфейс, указав тип указателя для сохранения.  
  
 `piid`  
 Указатель на IID `T`.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|Присваивает указатель на указатель на член.|  
  
## <a name="remarks"></a>Примечания  
 ATL использует `CComQIPtr` и [CComPtr](../../atl/reference/ccomptr-class.md) для управления указатели COM-интерфейса, которые являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Оба класса выполнить автоматический подсчет через вызовы ссылок `AddRef` и **выпуска**. Перегруженные операторы обрабатывать операции с указателями.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="ccomqiptr"></a>  CComQIPtr::CComQIPtr  
 Конструктор.  
  
```
CComQIPtr() throw();
CComQIPtr(T* lp) throw();
CComQIPtr(IUnknown* lp) throw();
CComQIPtr(const CComQIPtr<T, piid>& lp) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lp`  
 Используется для инициализации указателя интерфейса.  
  
 `T`  
 COM-интерфейса.  
  
 `piid`  
 Указатель на IID `T`.  
  
##  <a name="operator_eq"></a>  CComQIPtr::operator =  
 Оператор присваивания.  
  
```
T* operator= (T* lp) throw();
T* operator= (const CComQIPtr<T, piid>& lp) throw();
T* operator= (IUnknown* lp) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `lp`  
 Используется для инициализации указателя интерфейса.  
  
 `T`  
 COM-интерфейса.  
  
 `piid`  
 Указатель на IID `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на обновленный `CComQIPtr` объекта.  
  
## <a name="see-also"></a>См. также  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [Класс CComPtrBase](../../atl/reference/ccomptrbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)
