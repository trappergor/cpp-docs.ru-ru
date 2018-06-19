---
title: Класс CHeapPtr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a728f84a2eaa3f0138e2b0a95c25f8867c17432e
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32359947"
---
# <a name="cheapptr-class"></a>Класс CHeapPtr
Класс интеллектуальный указатель для управления указатели кучи.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template<typename T, class Allocator=CCRTAllocator>  
class CHeapPtr : public CHeapPtrBase<T, Allocator>
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип объекта для сохранения в куче.  
  
 `Allocator`  
 Класс выделения памяти для использования.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::CHeapPtr](#cheapptr)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::Allocate](#allocate)|Этот метод используется для выделения памяти для хранения объектов в куче.|  
|[CHeapPtr::Reallocate](#reallocate)|Этот метод вызывается для повторного выделения памяти в куче.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtr::operator =](#operator_eq)|Оператор присваивания.|  
  
## <a name="remarks"></a>Примечания  
 `CHeapPtr` является производным от [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md) и по умолчанию использует подпрограммы CRT (в [CCRTAllocator](../../atl/reference/ccrtallocator-class.md)) для выделения и освобождения памяти. Класс [CHeapPtrList](../../atl/reference/cheapptrlist-class.md) может использоваться для создания списка указателей кучи. См. также [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), использующий COM процедур выделения памяти.  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)  
  
 `CHeapPtr`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="allocate"></a>  CHeapPtr::Allocate  
 Этот метод используется для выделения памяти для хранения объектов в куче.  
  
```
bool Allocate(size_t nElements = 1) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Число элементов, используемых для вычисления объема памяти для выделения. Значение по умолчанию — 1.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объем памяти был успешно выделен, false в случае ошибки.  
  
### <a name="remarks"></a>Примечания  
 Подпрограммы распределителя используются для резервирование достаточного объема памяти в куче для хранения *nElement* объекты типа, определенного в конструкторе.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#77](../../atl/codesnippet/cpp/cheapptr-class_1.cpp)]  
  
##  <a name="cheapptr"></a>  CHeapPtr::CHeapPtr  
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
 Указатель кучи при необходимости могут создаваться с помощью существующего указателя, или `CHeapPtr` объекта. В этом случае новый `CHeapPtr` объект несет ответственность за управление новый указатель и ресурсы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#78](../../atl/codesnippet/cpp/cheapptr-class_2.cpp)]  
  
##  <a name="operator_eq"></a>  CHeapPtr::operator =  
 Оператор присвоения.  
  
```
CHeapPtr<T, Allocator>& operator=(
    CHeapPtr<T, Allocator>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Существующий объект `CHeapPtr`.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на обновленный `CHeapPtr`.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#80](../../atl/codesnippet/cpp/cheapptr-class_3.cpp)]  
  
##  <a name="reallocate"></a>  CHeapPtr::Reallocate  
 Этот метод вызывается для повторного выделения памяти в куче.  
  
```
bool Reallocate(size_t nElements) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nElements`  
 Новый номер элементы, используемые для вычисления объема памяти для выделения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если объем памяти был успешно выделен, false в случае ошибки.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#79](../../atl/codesnippet/cpp/cheapptr-class_4.cpp)]  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtrBase](../../atl/reference/cheapptrbase-class.md)   
 [Класс CCRTAllocator](../../atl/reference/ccrtallocator-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
