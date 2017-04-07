---
title: "Класс CAdapt | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAdapt
- ATLCOMCLI/ATL::CAdapt
- ATLCOMCLI/ATL::CAdapt::CAdapt
- ATLCOMCLI/ATL::CAdapt::m_T
dev_langs:
- C++
helpviewer_keywords:
- address-of operator
- adapter objects
- '& operator, address-of operator'
- CAdapt class
ms.assetid: 0bb695a5-72fe-43d1-8f39-7e4da6e34765
caps.latest.revision: 21
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: 8cdedc5cfac9d49df812ae6fcfcc548201b1edb5
ms.openlocfilehash: 84346b548e6d0fc7a1ce3078385aee45dfd0031e
ms.lasthandoff: 02/24/2017

---
# <a name="cadapt-class"></a>Класс CAdapt
Этот шаблон используется для создания оболочек классов, переопределяющих оператор взятия адреса, чтобы он возвращал нечто, отличное от адреса объекта.  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CAdapt
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Адаптированный тип.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAdapt::operator const T &](#operator_const_t_amp)|Возвращает `const` ссылку на `m_T`.|  
|[CAdapt::operator T &](#operator_t_amp)|Возвращает ссылку на `m_T`.|  
|[CAdapt::operator](#operator_lt)|Сравнивает объект адаптированного типа с `m_T`.|  
|[CAdapt::operator =](#operator_eq)|Присваивает `m_T` объект адаптированного типа.|  
|[CAdapt::operator ==](#operator_eq_eq)|Сравнивает объект адаптированного типа с `m_T`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Адаптируемые данные.|  
  
## <a name="remarks"></a>Примечания  
 `CAdapt`представляет собой простой шаблон, используемый для создания оболочек классов, переопределяющих оператор взятия адреса ( `operator &`) для возврата, отличный от адреса объекта. Примерами таких классов являются классы ATL `CComBSTR`, `CComPtr` и `CComQIPtr`, а также класс поддержки COM компилятора `_com_ptr_t`. Все эти классы переопределяют оператор взятия адреса, чтобы он возвращал адрес одного из своих данных-членов (`BSTR` в случае `CComBSTR` и указатель на интерфейс в случае других классов).  
  
 Основным назначением `CAdapt` является скрытие оператора взятия адреса, определенного классом `T`, при сохранении характеристик адаптированного класса. `CAdapt`выполняет эту роль, включая в себя открытый член [m_T](#m_t), типа `T`и определяя операторы преобразования, операторы сравнения и конструктор копии специализациями `CAdapt` следует рассматривать как, если они являются объектами типа `T`.  
  
 Класс адаптера `CAdapt` полезен, поскольку для некоторых классов стиля контейнера ожидается, что они могут получать адреса содержащихся в них объектов с помощью оператора взятия адреса. Переопределение оператора взятия адреса может нарушать это требование, поскольку обычно вызывает ошибки компиляции и не позволяет использовать неадаптированный тип с классами, которые ожидают, что он "просто будет работать". `CAdapt` предоставляет способ обойти эти проблемы.  
  
 Обычно `CAdapt` используется при необходимости хранить объекты `CComBSTR`, `CComPtr`, `CComQIPtr` или `_com_ptr_t` в классе стиля контейнера. Это часто требовалось для контейнеров стандартной библиотеки C++ до введения поддержки стандарта C++11; контейнеры стандартной библиотеки C++11 автоматически работают с типами, в которых оператор `operator&()` перегружен. Стандартной библиотеке это достигается внутренними средствами [std::AddressOf ()](http://msdn.microsoft.com/library/6243ddc8-486a-4961-8b0c-33e9dc2e0648) для получения истинных адресов объектов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="cadapt"></a>CAdapt::CAdapt  
 Конструкторы позволяют объектам адаптера по умолчанию создается, скопированные из объект адаптированного типа или скопирован из другого объекта адаптера.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Переменная типа адаптируемые копируются в объекте нового созданного адаптера.  
  
 *rSrCA*  
 Объект адаптера автономные данные которого следует скопировать (или переместить) в объекте нового созданного адаптера.  
  
##  <a name="m_t"></a>CAdapt::m_T  
 Содержит адаптируемые данные.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Примечания  
 Это **открытый** элемент данных может осуществляться непосредственно или косвенно с [оператор const T &](#operator_const_t_amp) и [оператор T &](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>CAdapt::operator const T&amp;  
 Возвращает **const** ссылки [m_T](#m_t) член, позволяя объекта адаптера обрабатывается, как если бы это был объект типа `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **const** ссылку на `m_T`.  
  
##  <a name="operator_t_amp"></a>CAdapt::operator T&amp;  
 Возвращает ссылку на [m_T](#m_t) член, позволяя объекта адаптера обрабатывается, как если бы это был объект типа `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `m_T`.  
  
##  <a name="operator_lt"></a>CAdapt::operator&lt;  
 Сравнивает объект адаптированного типа с [m_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Ссылка на объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат сравнения между `m_T` и `rSrc`.  
  
##  <a name="operator_eq"></a>CAdapt::operator =  
 Оператор присваивания назначает аргумента, `rSrc`, элемент данных [m_T](#m_t) и возвращает объект текущего адаптера.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Ссылка на объект адаптированного типа должен быть скопирован. 

 `rSrCA`
Ссылка на объект для перемещения. 
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект.  
  
##  <a name="operator_eq_eq"></a>CAdapt::operator ==  
 Сравнивает объект адаптированного типа с [m_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Параметры  
 `rSrc`  
 Ссылка на объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат сравнения между `m_T` и `rSrc`.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

