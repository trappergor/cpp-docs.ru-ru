---
title: "Класс CAutoPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
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
caps.latest.revision: 23
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 309a3d0ddceab2995c85e156c7db09ddd7edfa86
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

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
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::CAutoPtr](#cautoptr)|Конструктор.|  
|[CAutoPtr:: ~ CAutoPtr](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::Attach](#attach)|Вызовите этот метод, чтобы стать владельцем существующего указателя.|  
|[CAutoPtr::Detach](#detach)|Этот метод используется для освобождения владения указатель.|  
|[CAutoPtr::Free](#free)|Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoPtr`.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::operator T *](#operator_t_star)|Оператор приведения.|  
|[CAutoPtr::operator =](#operator_eq)|Оператор присваивания.|  
|[CAutoPtr::operator->](#operator_ptr)|Оператор указателя на член.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAutoPtr::m_p](#m_p)|Переменная указателя члена данных.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет методы для создания и управления смарт-указатель, который защитит от утечек памяти, автоматически освобождение ресурсов, если его использование выходит за пределы области.  
  
 Кроме того, `CAutoPtr`конструктор копии и передать владение оператор присваивания указателя, копирование исходного указателя на указатель назначения и задав для исходного указателя NULL. Поэтому невозможно иметь двух `CAutoPtr` каждый хранения тот же указатель, а это снижает вероятность удаления тот же указатель дважды.  
  
 `CAutoPtr`также упрощает создание коллекции указателей. Вместо создания производного класса коллекции и переопределение деструктор, проще сделать из коллекции `CAutoPtr` объектов. При удалении коллекции `CAutoPtr` будет выходят за пределы области действия и автоматически удалять сами объекты.  
  
 [CHeapPtr](../../atl/reference/cheapptr-class.md) и варианты работать так же, как `CAutoPtr`, за исключением того, что они выделяют и освобождают память, вместо функций различных кучи C++ **новый** и **удаление** операторы. [CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md) аналогичен `CAutoPtr`, с тем отличием, что он использует **vector new []** и **вектор delete []** выделения и освобождения памяти.  
  
 См. также [CAutoPtrArray](../../atl/reference/cautoptrarray-class.md) и [CAutoPtrList](../../atl/reference/cautoptrlist-class.md) при требуются массивы или списки смарт-указателей.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
## <a name="example"></a>Пример  
 [!code-cpp[NVC_ATL_Utilities&#74;](../../atl/codesnippet/cpp/cautoptr-class_1.cpp)]  
  
##  <a name="attach"></a>CAutoPtr::Attach  
 Вызовите этот метод, чтобы стать владельцем существующего указателя.  
  
```
void Attach(T* p) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 `CAutoPtr` Объекта будет стать владельцем этого указателя.  
  
### <a name="remarks"></a>Примечания  
 Если `CAutoPtr` объект становится владельцем указатель, он автоматически удалит указатель и все выделенные данные, если он выходит за пределы области. Если [CAutoPtr::Detach](#detach) является именем, программист снова данный ответственность за освобождение любой выделяются ресурсы.  
  
 В отладочных построениях, произойдет сбой утверждения, если [CAutoPtr::m_p](#m_p) член данных в данный момент указывает существующее значение, то есть не равен NULL.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="cautoptr"></a>CAutoPtr::CAutoPtr  
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
 Существующего указателя.  
  
 `TSrc`  
 Тип, который управляется другой `CAutoPtr`, используемый для инициализации текущего объекта.  
  
### <a name="remarks"></a>Примечания  
 `CAutoPtr` Объект может быть создан с помощью существующего указателя, в этом случае он передает владение указателем.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="dtor"></a>CAutoPtr:: ~ CAutoPtr  
 Деструктор  
  
```
~CAutoPtr() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Освобождает все ресурсы, выделенные. Вызовы [CAutoPtr::Free](#free).  
  
##  <a name="detach"></a>CAutoPtr::Detach  
 Этот метод используется для освобождения владения указатель.  
  
```
T* Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает копию указателя.  
  
### <a name="remarks"></a>Примечания  
 Освобождает владение указатель, задает [CAutoPtr::m_p](#m_p) переменной-члена данных NULL и возвращает копию указателя. После вызова метода **отсоединения**, на программиста, чтобы освободить все выделяется ресурсы по которому `CAutoPtr` объект ранее предполагается reponsibility.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="free"></a>CAutoPtr::Free  
 Вызовите этот метод, чтобы удалить объект, на который указывает `CAutoPtr`.  
  
```
void Free() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Объект, на который указывает `CAutoPtr` освобождается и [CAutoPtr::m_p](#m_p) переменной-члена данных задано значение NULL.  
  
##  <a name="m_p"></a>CAutoPtr::m_p  
 Переменная указателя члена данных.  
  
```
T* m_p;
```  
  
### <a name="remarks"></a>Примечания  
 Эта переменная-член содержит информацию об указателях.  
  
##  <a name="operator_eq"></a>CAutoPtr::operator =  
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
 Возвращает ссылку на **CAutoPtr\< T настроек**.  
  
### <a name="remarks"></a>Примечания  
 Оператор присваивания отсоединяет `CAutoPtr` объекта из любой текущий указатель и присоединяет новый указатель `p`, на его месте.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_ptr"></a>CAutoPtr::operator-&gt;  
 Оператор указателя на член.  
  
```
T* operator->() const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение [CAutoPtr::m_p](#m_p) переменной-члена данных.  
  
### <a name="remarks"></a>Примечания  
 Этот оператор используется для вызова метода в классе, на который указывает `CAutoPtr` объекта. В отладочных построениях, произойдет сбой утверждения, если `CAutoPtr` указывает на значение NULL.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
##  <a name="operator_t_star"></a>CAutoPtr::operator T *  
 Оператор приведения.  
  
```  
operator T* () const throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на объект типа данных, определенного в шаблоне класса.  
  
### <a name="example"></a>Пример  
 Пример см. в [CAutoPtr Обзор](../../atl/reference/cautoptr-class.md).  
  
## <a name="see-also"></a>См. также  
 [Класс CHeapPtr](../../atl/reference/cheapptr-class.md)   
 [Класс CAutoVectorPtr](../../atl/reference/cautovectorptr-class.md)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

