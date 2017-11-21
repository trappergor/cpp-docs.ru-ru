---
title: "Класс CHeapPtrBase | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase
- ATLCORE/ATL::CHeapPtrBase::AllocateBytes
- ATLCORE/ATL::CHeapPtrBase::Attach
- ATLCORE/ATL::CHeapPtrBase::Detach
- ATLCORE/ATL::CHeapPtrBase::Free
- ATLCORE/ATL::CHeapPtrBase::ReallocateBytes
- ATLCORE/ATL::CHeapPtrBase::m_pData
dev_langs: C++
helpviewer_keywords: CHeapPtrBase class
ms.assetid: 501ac1b2-fb34-4c72-b7e6-a4f1fc8fda21
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 9a9b99d487b75c0d51b9d526e848e823af787cc9
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
 Тип объекта для сохранения в куче.  
  
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
|[CHeapPtrBase::Detach](#detach)|Вызовите этот метод для освобождения владения указателя.|  
|[CHeapPtrBase::Free](#free)|Этот метод вызывается для удаления объекта, на который указывает `CHeapPtrBase`.|  
|[CHeapPtrBase::ReallocateBytes](#reallocatebytes)|Этот метод вызывается для повторного выделения памяти.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase::operator T *](#operator_t_star)|Оператор приведения.|  
|[CHeapPtrBase::operator &](#operator_amp)|& Оператор.|  
|[CHeapPtrBase::operator ->](#operator_ptr)|Оператор указателя на член.|  

  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CHeapPtrBase::m_pData](#m_pdata)|Переменная члена данных указателя.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс является основой несколько классов кучи смарт-указатель. Производные классы, например, [CHeapPtr](../../atl/reference/cheapptr-class.md) и [CComHeapPtr](../../atl/reference/ccomheapptr-class.md), добавить собственные конструкторы и операторы. См. Примеры реализации этих классов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** файле atlcore.h  
  
##  <a name="allocatebytes"></a>CHeapPtrBase::AllocateBytes  
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
 В отладочных построениях, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) переменной-члена в текущий момент направлен существующему значению; то есть, не равно NULL.  
  
##  <a name="attach"></a>CHeapPtrBase::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* pData) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pData`  
 `CHeapPtrBase` Объекта будет распоряжаться этот указатель.  
  
### <a name="remarks"></a>Примечания  
 Когда `CHeapPtrBase` принимает право на владение указатель, он автоматически удалит указателя и все выделенные данные при его выходит за пределы области.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CHeapPtrBase::m_pData](#m_pdata) переменной-члена в текущий момент направлен существующему значению; то есть, не равно NULL.  
  
##  <a name="dtor"></a>CHeapPtrBase:: ~ CHeapPtrBase  
 Деструктор  
  
```
~CHeapPtrBase() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все выделенные ресурсы.  
  
##  <a name="detach"></a>CHeapPtrBase::Detach  
 Вызовите этот метод для освобождения владения указателя.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указателем, задает [CHeapPtrBase::m_pData](#m_pdata) переменной-члена значение NULL и возвращает копию указателя.  
  
##  <a name="free"></a>CHeapPtrBase::Free  
 Этот метод вызывается для удаления объекта, на который указывает `CHeapPtrBase`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CHeapPtrBase` освобождается и [CHeapPtrBase::m_pData](#m_pdata) переменной-члена имеет значение NULL.  
  
##  <a name="m_pdata"></a>CHeapPtrBase::m_pData  
 Переменная члена данных указателя.  
  
```
T* m_pData;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="operator_amp"></a>CHeapPtrBase::operator&amp;  
 & Оператор.  
  
```
T** operator&() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает адрес объекта, на который указывает `CHeapPtrBase` объекта.  
  

##  <a name="operator_ptr"></a>CHeapPtrBase::operator-&gt;  

 Оператор указателя на член.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CHeapPtrBase::m_pData](#m_pdata) переменной-члена.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор используется для вызова метода в классе, который указывает `CHeapPtrBase` объекта. В отладочных построениях, произойдет сбой утверждения, если `CHeapPtrBase` указывает на значение NULL.  
  
##  <a name="operator_t_star"></a>CHeapPtrBase::operator T *  
 Оператор приведения.  
  
```  
operator T*() const throw();
```  
  
### <a name="remarks"></a>Примечания  
 Возвращает [CHeapPtrBase::m_pData](#m_pdata).  
  
##  <a name="reallocatebytes"></a>CHeapPtrBase::ReallocateBytes  
 Этот метод вызывается для повторного выделения памяти.  
  
```
bool ReallocateBytes(size_t nBytes) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `nBytes`  
 Новый объем памяти для выделения в байтах.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение true, если память успешно выделения false в противном случае.  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CComHeapPtr](../../atl/reference/ccomheapptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
