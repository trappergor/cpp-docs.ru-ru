---
title: "Класс CComQIPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: e2060a0be3f9780191c316c2df41115e66033d4d
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomqiptr-class"></a>Класс CComQIPtr
Класс интеллектуального указателя для управления указателей интерфейса СОМ.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T, const IID* piid= &__uuidof(T)>  
class CComQIPtr: public CComPtr<T>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 COM-интерфейс, указав тип указателя для сохранения.  
  
 `piid`  
 Указатель на идентификатор IID `T`.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComQIPtr::CComQIPtr](#ccomqiptr)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComQIPtr::operator =](#operator_eq)|Присваивает указатель на указатель элемента.|  
  
## <a name="remarks"></a>Примечания  
 Использует ATL `CComQIPtr` и [CComPtr](../../atl/reference/ccomptr-class.md) управление указателей интерфейса СОМ, которые являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md). Оба класса выполнения автоматического подсчета через вызовы ссылок `AddRef` и **версии**. Перегруженные операторы обрабатывать операции с указателями.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 [Класс CComPtr](../../atl/reference/ccomptr-class.md)  
  
 `CComQIPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="ccomqiptr"></a>CComQIPtr::CComQIPtr  
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
 Указатель на идентификатор IID `T`.  
  
##  <a name="operator_eq"></a>CComQIPtr::operator =  
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
 Указатель на идентификатор IID `T`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на обновленный `CComQIPtr` объекта.  
  
## <a name="see-also"></a>См. также  
 [CComPtr::CComPtr](../../atl/reference/ccomptr-class.md#ccomptr)   
 [CComQIPtr::CComQIPtr](#ccomqiptr)   
 [Класс CComPtrBase](../../atl/reference/ccomptrbase-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)   
 [Класс CComQIPtrElementTraits](../../atl/reference/ccomqiptrelementtraits-class.md)

