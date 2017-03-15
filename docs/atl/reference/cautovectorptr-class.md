---
title: "Класс CAutoVectorPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAutoVectorPtr
- ATL.CAutoVectorPtr
- ATL.CAutoVectorPtr<T>
- CAutoVectorPtr
- ATL::CAutoVectorPtr<T>
dev_langs:
- C++
helpviewer_keywords:
- CAutoVectorPtr class
ms.assetid: 0030362b-6bc4-4a47-9b5b-3c3899dceab4
caps.latest.revision: 20
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: bb4bbd110552d1e3cf604add44de7e428d2703ee
ms.lasthandoff: 02/24/2017

---
# <a name="cautovectorptr-class"></a>Класс CAutoVectorPtr
Этот класс представляет объект интеллектуального указателя с помощью вектора новых и удаление операторов.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T>  
class CAutoVectorPtr
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип указателя.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::CAutoVectorPtr](#cautovectorptr)|Конструктор.|  
|[CAutoVectorPtr:: ~ CAutoVectorPtr](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::Allocate](#allocate)|Этот метод вызывается для выделения памяти, необходимый для массива объектов, указываемых `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CAutoVectorPtr::Detach](#detach)|Этот метод используется для освобождения владения указатель.|  
|[CAutoVectorPtr::Free](#free)|Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoVectorPtr`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|Оператор приведения.|  
|[CAutoVectorPtr::operator =](#operator_eq)|Оператор присваивания.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|Переменная указателя члена данных.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления смарт-указатель, который защитит от утечек памяти, автоматически освобождение ресурсов, если его использование выходит за пределы области. `CAutoVectorPtr`аналогичен `CAutoPtr`, с тем отличием, что `CAutoVectorPtr` использует [vector new []](../../standard-library/new-operators.md#operator_new_arr) и [вектор delete []](../../standard-library/new-operators.md#operator_delete_arr) для выделения и освобождения памяти, а не C++ **новый** и **удаление** операторы. В разделе [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) если коллекцию классов `CAutoVectorPtr` являются обязательными.  

  
 В разделе [CAutoPtr](../../atl/reference/cautoptr-class.md) пример использования класса смарт-указатель.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="a-nameallocatea--cautovectorptrallocate"></a><a name="allocate"></a>CAutoVectorPtr::Allocate  
 Этот метод вызывается для выделения памяти, необходимый для массива объектов, указываемых `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Количество элементов в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если память успешно выделен, значение false в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) существующему значению в настоящее время указывает переменную-член; то есть, не равно NULL.  
  
##  <a name="a-nameattacha--cautovectorptrattach"></a><a name="attach"></a>CAutoVectorPtr::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 `CAutoVectorPtr` Объекта будет стать владельцем этого указателя.  
  
### <a name="remarks"></a>Примечания  
 Если `CAutoVectorPtr` объект становится владельцем указатель, он автоматически удалит указатель и все выделенные данные, если он выходит за пределы области. Если [CAutoVectorPtr::Detach](#detach) является именем, программист снова данный ответственность за освобождение любой выделяются ресурсы.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) существующему значению в настоящее время указывает переменную-член; то есть, не равно NULL.  
  
##  <a name="a-namecautovectorptra--cautovectorptrcautovectorptr"></a><a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr  
 Конструктор.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Существующего указателя.  
  
### <a name="remarks"></a>Примечания  
 `CAutoVectorPtr` Объект может быть создан с помощью существующего указателя, в этом случае он передает владение указателем.  
  
##  <a name="a-namedtora--cautovectorptrcautovectorptr"></a><a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr  
 Деструктор  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные. Вызовы [CAutoVectorPtr::Free](#free).  
  
##  <a name="a-namedetacha--cautovectorptrdetach"></a><a name="detach"></a>CAutoVectorPtr::Detach  
 Этот метод используется для освобождения владения указатель.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указатель, задает [CAutoVectorPtr::m_p](#m_p) переменной-члена NULL и возвращает копию указателя. После вызова метода **отсоединения**, на программиста, чтобы освободить все выделяется ресурсы по которому `CAutoVectorPtr` объект может ранее берут на себя ответственность.  
  
##  <a name="a-namefreea--cautovectorptrfree"></a><a name="free"></a>CAutoVectorPtr::Free  
 Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CAutoVectorPtr` освобождается и [CAutoVectorPtr::m_p](#m_p) переменной-члена имеет значение NULL.  
  
##  <a name="a-namempa--cautovectorptrmp"></a><a name="m_p"></a>CAutoVectorPtr::m_p  
 Переменная указателя члена данных.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="a-nameoperatoreqa--cautovectorptroperator-"></a><a name="operator_eq"></a>CAutoVectorPtr::operator =  
 Оператор присваивания.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на **CAutoVectorPtr\< T настроек**.  
  
### <a name="remarks"></a>Примечания  
 Оператор присваивания отсоединяет `CAutoVectorPtr` объекта из любой текущий указатель и присоединяет новый указатель `p`, на его месте.  
  
##  <a name="a-nameoperatortstara--cautovectorptroperator-t-"></a><a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 Оператор приведения.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает указатель на объект типа данных, определенного в шаблоне класса.  
  
## <a name="see-also"></a>См. также  
 [Класс CAutoPtr](../../atl/reference/cautoptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

