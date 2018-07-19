---
title: Класс CAdapt | Документация Майкрософт
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 5bf0739c92513519147e9aed3b88210c4f61d0b4
ms.sourcegitcommit: 7d68f8303e021e27dc8f4d36e764ed836e93d24f
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 07/06/2018
ms.locfileid: "37882986"
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
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAdapt::CAdapt](#cadapt)|Конструктор.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAdapt::operator const T &](#operator_const_t_amp)|Возвращает **const** ссылка `m_T`.|  
|[CAdapt::operator T &](#operator_t_amp)|Возвращает ссылку на `m_T`.|  
|[CAdapt::operator <](#operator_lt)|Сравнивает объект адаптированного типа с `m_T`.|  
|[CAdapt::operator =](#operator_eq)|Присваивает `m_T` объект адаптированного типа.|  
|[CAdapt::operator ==](#operator_eq_eq)|Сравнивает объект адаптированного типа с `m_T`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CAdapt::m_T](#m_t)|Адаптируемые данные.|  
  
## <a name="remarks"></a>Примечания  
 `CAdapt` представляет собой простой шаблон, который используется для создания оболочек классов, переопределяющих оператор взятия адреса (`operator &`), чтобы он возвращал нечто, отличное от адреса объекта. Примерами таких классов являются классы ATL `CComBSTR`, `CComPtr` и `CComQIPtr`, а также класс поддержки COM компилятора `_com_ptr_t`. Все эти классы переопределяют оператор взятия адреса, чтобы получить адрес одного из своих данных-членов (BSTR в случае использования `CComBSTR`и указатель интерфейса, в случае других классов).  
  
 Основным назначением `CAdapt` является скрытие оператора взятия адреса, определенного классом `T`, при сохранении характеристик адаптированного класса. `CAdapt` удовлетворяющий этой роли, открытый член, удерживая [m_T](#m_t), типа `T`и определяя операторы преобразования, операторы сравнения и конструктор копии специализациями `CAdapt` рассматриваться, как если бы они объекты типа `T`.  
  
 Класс адаптера `CAdapt` полезен, поскольку для некоторых классов стиля контейнера ожидается, что они могут получать адреса содержащихся в них объектов с помощью оператора взятия адреса. Переопределение оператора взятия адреса может нарушать это требование, поскольку обычно вызывает ошибки компиляции и не позволяет использовать неадаптированный тип с классами, которые ожидают, что он "просто будет работать". `CAdapt` предоставляет способ обойти эти проблемы.  
  
 Обычно `CAdapt` используется при необходимости хранить объекты `CComBSTR`, `CComPtr`, `CComQIPtr` или `_com_ptr_t` в классе стиля контейнера. Это часто требовалось для контейнеров стандартной библиотеки C++ до введения поддержки стандарта C++11; контейнеры стандартной библиотеки C++11 автоматически работают с типами, в которых оператор `operator&()` перегружен. Стандартной библиотеке это достигается внутренними средствами [std::addressof](../../standard-library/memory-functions.md#addressof) для получения истинных адресов объектов.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlcomcli.h  
  
##  <a name="cadapt"></a>  CAdapt::CAdapt  
 Конструкторы позволяют объектам адаптера по умолчанию создан, скопированные из объект адаптированного типа или скопирован из другого объекта адаптера.  
  
```
CAdapt();
CAdapt(const T& rSrc);
CAdapt(const CAdapt& rSrCA);
CAdapt(T&& rSrCA);  // (Visual Studio 2017)
CAdapt(CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 *rSrc*  
 Переменная типа, адаптации для копирования в объект нового созданного адаптера.  
  
 *rSrCA*  
 Объект адаптера, содержащиеся данные следует копировать (или перемещать) в объект нового созданного адаптера.  
  
##  <a name="m_t"></a>  CAdapt::m_T  
 Содержит адаптируемые данные.  
  
```
T m_T;
```  
  
### <a name="remarks"></a>Примечания  
 Это **открытый** элемент данных может осуществляться прямо или косвенно с [оператор const T &](#operator_const_t_amp) и [оператор T &](#operator_t_amp).  
  
##  <a name="operator_const_t_amp"></a>  CAdapt::operator const T&amp;  
 Возвращает **const** ссылка [m_T](#m_t) член, позволяя объекте адаптера рассматриваться, как если бы это был объект типа `T`.  
  
```  
operator const T&() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Объект **const** ссылка `m_T`.  
  
##  <a name="operator_t_amp"></a>  CAdapt::operator T&amp;  
 Возвращает ссылку на [m_T](#m_t) член, позволяя объекте адаптера рассматриваться, как если бы это был объект типа `T`.  
  
```  
operator T&();
```     
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылку на `m_T`.  
  
##  <a name="operator_lt"></a>  CAdapt::operator &lt;  
 Сравнивает объект адаптированного типа с [m_T](#m_t).  
  
```
bool operator<(const T& rSrc) const;
```  
  
### <a name="parameters"></a>Параметры  
 *rSrc*  
 Ссылка на объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат сравнения между `m_T` и *rSrc*.  
  
##  <a name="operator_eq"></a>  CAdapt::operator =  
 Оператор присваивания присваивает аргумент, *rSrc*, элемент данных, [m_T](#m_t) и возвращает текущий объект адаптера.  
  
```
CAdapt& operator= (const T& rSrc);
CAdapt& operator= (T&& rSrCA); // (Visual Studio 2017)
CAdapt& operator= (CAdapt<T>&& rSrCA) noexcept; // (Visual Studio 2017)
```  
  
### <a name="parameters"></a>Параметры  
 *rSrc*  
 Ссылка на объект адаптированного типа для копирования. 

 *rSrCA* ссылку на объект для перемещения. 
  
### <a name="return-value"></a>Возвращаемое значение  
 Ссылка на текущий объект.  
  
##  <a name="operator_eq_eq"></a>  CAdapt::operator ==  
 Сравнивает объект адаптированного типа с [m_T](#m_t).  
  
```
bool operator== (const T& rSrc) const;
```  
  
### <a name="parameters"></a>Параметры  
 *rSrc*  
 Ссылка на объект для сравнения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Результат сравнения между `m_T` и *rSrc*.  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)
