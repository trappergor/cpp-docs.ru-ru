---
title: "Класс CAutoVectorPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::CAutoVectorPtr
- ATLBASE/ATL::CAutoVectorPtr::Allocate
- ATLBASE/ATL::CAutoVectorPtr::Attach
- ATLBASE/ATL::CAutoVectorPtr::Detach
- ATLBASE/ATL::CAutoVectorPtr::Free
- ATLBASE/ATL::CAutoVectorPtr::m_p
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 66798adc96121837b4ac2dd238b9887d3c5b7eef
ms.openlocfilehash: 8234018b2f6faf8585186491413ecbd688a3b32f
ms.contentlocale: ru-ru
ms.lasthandoff: 04/29/2017

---
# <a name="cautovectorptr-class"></a>Класс CAutoVectorPtr
Этот класс представляет объект интеллектуального указателя с помощью нового вектора и удаление операторов.  
  
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
|[CAutoVectorPtr::Allocate](#allocate)|Вызовите этот метод, чтобы выделить память, необходимую для массива объектов, указываемых `CAutoVectorPtr`.|  
|[CAutoVectorPtr::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CAutoVectorPtr::Detach](#detach)|Вызовите этот метод для освобождения владения указателя.|  
|[CAutoVectorPtr::Free](#free)|Этот метод вызывается для удаления объекта, на который указывает `CAutoVectorPtr`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::operator T *](#operator_t__star)|Оператор приведения.|  
|[CAutoVectorPtr::operator =](#operator_eq)|Оператор присваивания.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoVectorPtr::m_p](#m_p)|Переменная члена данных указателя.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления смарт-указатель, который поможет обеспечить защиту от утечек памяти, автоматически освобождение ресурсов, если его использование выходит за пределы области. `CAutoVectorPtr`Аналогично `CAutoPtr`, единственное отличие состоит, `CAutoVectorPtr` использует [вектор new &#91; &#93;](../../standard-library/new-operators.md#op_new_arr) и [vector delete &#91; &#93;](../../standard-library/new-operators.md#op_delete_arr) выделения и освобождения памяти, вместо C++ **новый** и **удалить** операторы. В разделе [CAutoVectorPtrElementTraits](../../atl/reference/cautovectorptrelementtraits-class.md) если коллекцию классов `CAutoVectorPtr` являются обязательными.  

  
 В разделе [CAutoPtr](../../atl/reference/cautoptr-class.md) в качестве примера использования класса интеллектуального указателя.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="allocate"></a>CAutoVectorPtr::Allocate  
 Вызовите этот метод, чтобы выделить память, необходимую для массива объектов, указываемых `CAutoVectorPtr`.  
  
```
bool Allocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Количество элементов в массиве.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если память успешно выделен, false в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) переменной-члена в текущий момент направлен существующему значению; то есть, не равно NULL.  
  
##  <a name="attach"></a>CAutoVectorPtr::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 `CAutoVectorPtr` Объекта будет распоряжаться этот указатель.  
  
### <a name="remarks"></a>Примечания  
 Когда `CAutoVectorPtr` принимает право на владение указатель, он автоматически удалит указателя и все выделенные данные при его выходит за пределы области. Если [CAutoVectorPtr::Detach](#detach) — вызывается, программист снова данный ответственности за любой освобождение выделяется ресурсов.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoVectorPtr::m_p](#m_p) переменной-члена в текущий момент направлен существующему значению; то есть, не равно NULL.  
  
##  <a name="cautovectorptr"></a>CAutoVectorPtr::CAutoVectorPtr  
 Конструктор.  
  
```
CAutoVectorPtr() throw();
explicit CAutoVectorPtr(T* p) throw();
CAutoVectorPtr(CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Существующий указатель.  
  
### <a name="remarks"></a>Примечания  
 `CAutoVectorPtr` Объект может быть создан с помощью указателя на существующих, в противном случае он передает владение указателем.  
  
##  <a name="dtor"></a>CAutoVectorPtr:: ~ CAutoVectorPtr  
 Деструктор  
  
```
~CAutoVectorPtr() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные. Вызовы [CAutoVectorPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoVectorPtr::Detach  
 Вызовите этот метод для освобождения владения указателя.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указателем, задает [CAutoVectorPtr::m_p](#m_p) переменной-члена значение NULL и возвращает копию указателя. После вызова метода **отсоединения**, он является на программиста, чтобы освободить все ресурсы выделяются по которому `CAutoVectorPtr` объект ранее предполагается ответственности.  
  
##  <a name="free"></a>CAutoVectorPtr::Free  
 Этот метод вызывается для удаления объекта, на который указывает `CAutoVectorPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CAutoVectorPtr` освобождается и [CAutoVectorPtr::m_p](#m_p) переменной-члена имеет значение NULL.  
  
##  <a name="m_p"></a>CAutoVectorPtr::m_p  
 Переменная члена данных указателя.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="operator_eq"></a>CAutoVectorPtr::operator =  
 Оператор присваивания.  
  
```
CAutoVectorPtr<T>& operator= (CAutoVectorPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на **CAutoVectorPtr\< T >**.  
  
### <a name="remarks"></a>Примечания  
 Оператор присваивания отсоединяет `CAutoVectorPtr` объекта из любого текущего указателя и присоединяет новый указатель `p`, вместо него.  
  
##  <a name="operator_t__star"></a>CAutoVectorPtr::operator T *  
 Оператор приведения.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает указатель на тип объекта данных, определенные в шаблоне класса.  
  
## <a name="see-also"></a>См. также  
 [Класс CAutoPtr](../../atl/reference/cautoptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

