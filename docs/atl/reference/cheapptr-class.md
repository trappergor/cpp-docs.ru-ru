---
title: "Класс CHeapPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtr
- ATLCORE/ATL::CHeapPtr
- ATLCORE/ATL::CHeapPtr::CHeapPtr
- ATLCORE/ATL::CHeapPtr::Allocate
- ATLCORE/ATL::CHeapPtr::Reallocate
dev_langs:
- C++
helpviewer_keywords:
- CHeapPtr class
ms.assetid: e5c5bfd4-9bf1-4164-8a83-8155fe253454
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
ms.openlocfilehash: 41334cd7497c9e21d1cf047d7ab304864f663758
ms.lasthandoff: 02/24/2017

---
# <a name="cheapptr-class"></a>Класс CHeapPtr
Класс интеллектуального указателя для управления кучей указателей.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта, который должен храниться в куче.  
  
 `Allocator`  
 Класс выделения памяти для использования.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|Этот метод используется для выделения памяти в куче для хранения объектов.|  
|[CHeapPtr::Reallocate](#reallocate)|Этот метод вызывается для повторного выделения памяти в куче.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|Оператор присваивания.|  
  
## <a name="remarks"></a>Примечания  
 `CHeapPtr`является производным от [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) и по умолчанию использует подпрограммы CRT (в [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) для выделения и освобождения памяти. Класс [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) может использоваться для создания списка указателей кучи. См. также [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), использующий COM процедур выделения памяти.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="allocate"></a>CHeapPtr::Allocate  
 Этот метод используется для выделения памяти в куче для хранения объектов.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Число элементов, используемых для расчета объема выделяемой памяти. Значение по умолчанию — 1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объем памяти был успешно выделен, значение false в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Подпрограммы распределителя позволяют зарезервировать достаточно памяти в куче для хранения *nElement* объектов типа, определенного в конструкторе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#77;](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>CHeapPtr::CHeapPtr  
 Конструктор.  
  
```
CHeapPtr() throw();
explicit CHeapPtr(T* p) throw();
CHeapPtr(CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на существующей кучи или `CHeapPtr`.  
  
### <a name="remarks"></a>Примечания  
 Указатель кучи при необходимости могут создаваться с помощью указателя на существующий или `CHeapPtr` объекта. В этом случае новый `CHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#78;](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>CHeapPtr::operator =  
 Оператор присвоения.  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Существующий объект `CHeapPtr`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленную `CHeapPtr`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#80;](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>CHeapPtr::Reallocate  
 Этот метод вызывается для повторного выделения памяти в куче.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Новый номер элементы, используемые для расчета объема выделяемой памяти.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объем памяти был успешно выделен, значение false в случае сбоя.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#79;](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
 [Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

