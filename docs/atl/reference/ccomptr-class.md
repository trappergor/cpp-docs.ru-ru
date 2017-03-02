---
title: "Класс CComPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComPtr
dev_langs:
- C++
helpviewer_keywords:
- CComPtr class
ms.assetid: 22d9ea8d-ed66-4c34-940f-141db11e83bd
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: ae7bb5e85f23492bdbef4af86d9f68fa83c991e2
ms.lasthandoff: 02/24/2017

---
# <a name="ccomptr-class"></a>Класс CComPtr
Класс интеллектуального указателя для управления указателей интерфейса СОМ.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<class T>  
class CComPtr
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 COM-интерфейс, указав тип указателя для сохранения.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtr::CComPtr](#ccomptr)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComPtr::operator =](#operator_eq)|Присваивает указатель на указатель элемента.|  
  
## <a name="remarks"></a>Примечания  
 Использует ATL `CComPtr` и [CComQIPtr](../../atl/reference/ccomqiptr-class.md) для управления указателей интерфейса СОМ. Являются производными от [CComPtrBase](../../atl/reference/ccomptrbase-class.md), и оба выполняют автоматическим подсчетом ссылок.  
  
 **CComPtr** и [CComQIPtr](../../atl/reference/ccomqiptr-class.md) классов может помочь избежать утечек памяти, выполняя автоматическим подсчетом ссылок.  Следующие функции оба выполняют логические операции; Однако обратите внимание, как вторая версия может быть меньше ошибок с помощью **CComPtr** класса:  
  
 [!code-cpp[NVC_ATL_Utilities&#130;](../../atl/codesnippet/cpp/ccomptr-class_1.cpp)]  
  
 [!code-cpp[NVC_ATL_Utilities&#131;](../../atl/codesnippet/cpp/ccomptr-class_2.cpp)]  
  
 В отладочных построениях свяжите atlsd.lib для трассировки кода.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CComPtrBase](../../atl/reference/ccomptrbase-class.md)  
  
 `CComPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-nameccomptra--ccomptrccomptr"></a><a name="ccomptr"></a>CComPtr::CComPtr  
 Конструктор.  
  
```
CComPtr() throw ();
CComPtr(T* lp) throw ();
CComPtr (const CComPtr<T>& lp) throw ();
```  
  
### <a name="parameters"></a>Параметры  
 `lp`  
 Используется для инициализации указателя интерфейса.  
  
 `T`  
 COM-интерфейса.  
  
##  <a name="a-nameoperatoreqa--ccomptroperator-"></a><a name="operator_eq"></a>CComPtr::operator =  
 Оператор присвоения.  
  
```
T* operator= (T* lp) throw ();
T* operator= (const CComPtr<T>& lp) throw ();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на обновленный `CComPtr` объекта  
  
### <a name="remarks"></a>Примечания  
 Это операция AddRefs новый объект и выпусках существующий объект, если он существует.  
  
## <a name="see-also"></a>См. также  
 [CComPtr::CComPtr](#ccomptr)   
 [CComQIPtr::CComQIPtr](../../atl/reference/ccomqiptr-class.md#ccomqiptr)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

