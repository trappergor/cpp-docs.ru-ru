---
title: "Класс CHeapPtrBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CHeapPtrBase
- ATL::CHeapPtrBase
- CHeapPtrBase
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 8084104489f6f1e2358ce0cbb573f4e20a0c4fce
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptrbase-class"></a>Класс CHeapPtrBase
Этот класс является основой несколько классов кучи смарт-указатель.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T, class Allocator = CCRTAllocator>  
class CHeapPtrBase
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, который должен храниться в куче.  
  
 `Allocator`  
 Класс выделения памяти для использования. По умолчанию подпрограммы CRT используются для выделения и освобождения памяти.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase:: ~ CHeapPtrBase](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase::AllocateBytes](#allocatebytes)|Этот метод используется для выделения памяти.|  
|[CHeapPtrBase::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CHeapPtrBase::Detach](#detach)|Этот метод используется для освобождения владения указатель.|  
|[CHeapPtrBase::Free](#free)|Вызовите этот метод, чтобы удалить объект, на который указывает `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Этот метод вызывается для повторного выделения памяти.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|Оператор приведения.|  
|[CHeapPtrBase::operator &](#operator_amp)|& Оператор.|  
|[CHeapPtrBase::operator->](#operator_ptr)|Оператор указателя на член.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|Переменная указателя члена данных.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является основой несколько классов кучи смарт-указатель. Производные классы, например, [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), добавлять собственные конструкторы и операторы. В разделе Примеры реализации этих классов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="a-nameallocatebytesa--cheapptrbaseallocatebytes"></a><a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes  
 Этот метод используется для выделения памяти.  
  
```
bool AllocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Число байтов памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если память успешно выделения false в противном случае.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) существующему значению в настоящее время указывает переменную-член; то есть, не равно NULL.  
  
##  <a name="a-nameattacha--cheapptrbaseattach"></a><a name="attach"></a>CHeapPtrBase::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 `CHeapPtrBase` Объекта будет стать владельцем этого указателя.  
  
### <a name="remarks"></a>Примечания  
 Если `CHeapPtrBase` объект становится владельцем указатель, он автоматически удалит указатель и все выделенные данные, если он выходит за пределы области.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) существующему значению в настоящее время указывает переменную-член; то есть, не равно NULL.  
  
##  <a name="a-namedtora--cheapptrbasecheapptrbase"></a><a name="dtor"></a>CHeapPtrBase:: ~ CHeapPtrBase  
 Деструктор  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="a-namedetacha--cheapptrbasedetach"></a><a name="detach"></a>CHeapPtrBase::Detach  
 Этот метод используется для освобождения владения указатель.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указатель, задает [CHeapPtrBase::m_pData](#m_pdata) переменной-члена NULL и возвращает копию указателя.  
  
##  <a name="a-namefreea--cheapptrbasefree"></a><a name="free"></a>CHeapPtrBase::Free  
 Вызовите этот метод, чтобы удалить объект, на который указывает `CHeapPtrBase`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CHeapPtrBase` освобождается и [CHeapPtrBase::m_pData](#m_pdata) переменной-члена имеет значение NULL.  
  
##  <a name="a-namempdataa--cheapptrbasempdata"></a><a name="m_pdata"></a>CHeapPtrBase::m_pData  
 Переменная указателя члена данных.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="a-nameoperatorampa--cheapptrbaseoperator-amp"></a><a name="operator_amp"></a>CHeapPtrBase::operator&amp;  
 & Оператор.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес объекта, на который указывает `CHeapPtrBase` объекта.  
  

##  <a name="a-nameoperatorptra--cheapptrbaseoperator--gt"></a><a name="operator_ptr"></a>CHeapPtrBase::operator-&gt;  

 Оператор указателя на член.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CHeapPtrBase::m_pData](#m_pdata) переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор используется для вызова метода в классе, на который указывает `CHeapPtrBase` объекта. В отладочных построениях, произойдет сбой утверждения, если `CHeapPtrBase` указывает на значение NULL.  
  
##  <a name="a-nameoperatortstara--cheapptrbaseoperator-t"></a><a name="operator_t_star"></a>CHeapPtrBase::operator T *  
 Оператор приведения.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает [CHeapPtrBase::m_pData](#m_pdata).  
  
##  <a name="a-namereallocatebytesa--cheapptrbasereallocatebytes"></a><a name="reallocatebytes"></a>CHeapPtrBase::ReallocateBytes  
 Этот метод вызывается для повторного выделения памяти.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Новый объем памяти, выделенной в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если память успешно выделения false в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

