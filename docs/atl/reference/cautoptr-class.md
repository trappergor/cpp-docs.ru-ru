---
title: Класс CAutoPtr | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- CAutoPtr
- ATLBASE/ATL::CAutoPtr
- ATLBASE/ATL::CAutoPtr::CAutoPtr
- ATLBASE/ATL::CAutoPtr::Attach
- ATLBASE/ATL::CAutoPtr::Detach
- ATLBASE/ATL::CAutoPtr::Free
- ATLBASE/ATL::CAutoPtr::m_p
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtr class
ms.assetid: 08988d53-4fb0-4711-bdfc-8ac29c63f410
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: edf1baff50541dd5f16c27205f300558558d6f92
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/03/2018
ms.locfileid: "32363204"
---
# <a name="cautoptr-class"></a>Класс CAutoPtr
Этот класс представляет объект интеллектуального указателя.  
  
> [!IMPORTANT]
>  Этот класс и его члены не может использоваться в приложениях, выполняемых в среде выполнения Windows.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <typename T>  
class CAutoPtr
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип указателя.  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|Конструктор.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CAutoPtr::Detach](#detach)|Вызовите этот метод для освобождения владения указателя.|  
|[CAutoPtr::Free](#free)|Этот метод вызывается для удаления объекта, на который указывает `CAutoPtr`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|Оператор приведения.|  
|[CAutoPtr::operator =](#operator_eq)|Оператор присваивания.|  
|[CAutoPtr::operator ->](#operator_ptr)|Оператор указателя на член.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|Переменная члена данных указателя.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления смарт-указатель, который поможет обеспечить защиту от утечек памяти, автоматически освобождение ресурсов, если его использование выходит за пределы области.  
  
 Кроме того, `CAutoPtr`конструктор копирования и передать владение оператор назначения указателя, копирование исходного указателя на указатель назначения и задав исходного указателя NULL. Поэтому невозможно иметь два `CAutoPtr` объекты каждого хранения тот же указатель и повышает вероятность удаления тот же указатель дважды.  
  
 `CAutoPtr` также упрощает создание коллекции указателей. Вместо создания производного класса коллекции, а также путем переопределения деструктор, проще сделать из коллекции `CAutoPtr` объектов. При удалении коллекции `CAutoPtr` будет выходят за пределы области действия и автоматически удалять сами объекты.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) и варианты работать так же, как `CAutoPtr`, за исключением того, что они выделяют и освобождают память, вместо функций различных кучи C++ **новый** и **удалить** операторы. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) аналогичен `CAutoPtr`, единственное отличие состоит в том, что она использует **vector new []** и **вектор delete []** выделения и освобождения памяти.  
  
 См. также [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) при требуются массивов или списков интеллектуальных указателей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities#74](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>  CAutoPtr::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 `CAutoPtr` Объекта будет распоряжаться этот указатель.  
  
### <a name="remarks"></a>Примечания  
 Когда `CAutoPtr` принимает право на владение указатель, он автоматически удалит указателя и все выделенные данные при его выходит за пределы области. Если [CAutoPtr::Detach](#detach) — вызывается, программист снова данный ответственности за любой освобождение выделяется ресурсов.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoPtr::m_p](#m_p) данные-член в текущий момент направлен существующему значению; то есть, не равно NULL.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="cautoptr"></a>  CAutoPtr::CAutoPtr  
 Конструктор.  
  
```
CAutoPtr() throw();
explicit CAutoPtr(T* p) throw();

template<typename TSrc>
CAutoPtr(CAutoPtr<TSrc>& p) throw();

template<> 
CAutoPtr(CAutoPtr<T>& p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Существующий указатель.  
  
 `TSrc`  
 Тип, который находится под управлением другой `CAutoPtr`, используемый для инициализации текущего объекта.  
  
### <a name="remarks"></a>Примечания  
 `CAutoPtr` Объект может быть создан с помощью указателя на существующих, в противном случае он передает владение указателем.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="dtor"></a>  CAutoPtr:: ~ CAutoPtr  
 Деструктор  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные. Вызовы [CAutoPtr::Free](#free).  
  
##  <a name="detach"></a>  CAutoPtr::Detach  
 Вызовите этот метод для освобождения владения указателя.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указателем, задает [CAutoPtr::m_p](#m_p) переменной-члена данных значение NULL и возвращает копию указателя. После вызова метода **отсоединения**, он является на программиста, чтобы освободить все ресурсы выделяются по которому `CAutoPtr` объект ранее предполагается reponsibility.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="free"></a>  CAutoPtr::Free  
 Этот метод вызывается для удаления объекта, на который указывает `CAutoPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CAutoPtr` освобождается и [CAutoPtr::m_p](#m_p) переменной-члена данных задано значение NULL.  
  
##  <a name="m_p"></a>  CAutoPtr::m_p  
 Переменная члена данных указателя.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="operator_eq"></a>  CAutoPtr::operator =  
 Оператор присваивания.  
  
```
template<>
CAutoPtr<T>& operator= (CAutoPtr<T>& p);

template<typename TSrc>
CAutoPtr<T>& operator= (CAutoPtr<TSrc>& p);
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель.  
  
 `TSrc`  
 Тип класса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает ссылку на **CAutoPtr\< T >**.  
  
### <a name="remarks"></a>Примечания  
 Оператор присваивания отсоединяет `CAutoPtr` объекта из любого текущего указателя и присоединяет новый указатель `p`, вместо него.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_ptr"></a>  CAutoPtr::operator-&gt;  
 Оператор указателя на член.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CAutoPtr::m_p](#m_p) переменной-члена данных.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор используется для вызова метода в классе, который указывает `CAutoPtr` объекта. В отладочных построениях, произойдет сбой утверждения, если `CAutoPtr` указывает на значение NULL.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_t_star"></a>  CAutoPtr::operator T *  
 Оператор приведения.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на тип объекта данных, определенные в шаблоне класса.  
  
### <a name="example"></a>Пример  
 См. пример в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)
