---
title: "Класс CComGITPtr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComGITPtr
- ATLBASE/ATL::CComGITPtr
- ATLBASE/ATL::CComGITPtr::CComGITPtr
- ATLBASE/ATL::CComGITPtr::Attach
- ATLBASE/ATL::CComGITPtr::CopyTo
- ATLBASE/ATL::CComGITPtr::Detach
- ATLBASE/ATL::CComGITPtr::GetCookie
- ATLBASE/ATL::CComGITPtr::Revoke
- ATLBASE/ATL::CComGITPtr::m_dwCookie
dev_langs:
- C++
helpviewer_keywords:
- CComGITPtr class
ms.assetid: af895acb-525a-4555-bb67-b241b7df515b
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 9fe9d9f6d03a6d72c1ce3332419c738570a53803
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="ccomgitptr-class"></a>Класс CComGITPtr
Этот класс предоставляет методы для работы с указатели интерфейса и глобальной таблицы интерфейсов (GIT).  
  
## <a name="syntax"></a>Синтаксис  
  
```
template <class T>  
class CComGITPtr
```  
  
#### <a name="parameters"></a>Параметры  
 `T`  
 Тип указателя интерфейса должны храниться в GIT.  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComGITPtr::CComGITPtr](#ccomgitptr)|Конструктор.|  
|[CComGITPtr:: ~ CComGITPtr](#dtor)|Деструктор|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComGITPtr::Attach](#attach)|Этот метод вызывается для регистрации указателя интерфейса в глобальной таблицы интерфейсов (GIT).|  
|[CComGITPtr::CopyTo](#copyto)|Этот метод служит для копирования передан указатель интерфейса из глобальной таблицы интерфейсов (GIT).|  
|[CComGITPtr::Detach](#detach)|Вызов этого метода позволяет отделить интерфейс от `CComGITPtr` объекта.|  
|[CComGITPtr::GetCookie](#getcookie)|Вызовите этот метод для возврата файла cookie из `CComGITPtr` объекта.|  
|[CComGITPtr::Revoke](#revoke)|Этот метод используется для удаления интерфейс из глобальной таблицы интерфейсов (GIT).|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComGITPtr::operator DWORD](#operator_dword)|Возвращает файл cookie из `CComGITPtr` объекта.|  
|[CComGITPtr::operator =](#operator_eq)|Оператор присвоения.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CComGITPtr::m_dwCookie](#m_dwcookie)|Файл cookie.|  
  
## <a name="remarks"></a>Примечания  
 Объекты, которые статистическая обработка свободного упаковщик в режиме потока и необходимо использовать указатели на интерфейс, полученные от других объектов следует выполнить дополнительные шаги, чтобы убедиться, что интерфейсы маршалируются правильно. Обычно это подразумевает хранение указателей интерфейса в GIT и получение указателя из GIT каждый раз, в которой он используется. Класс `CComGITPtr` предназначено для использования указателей интерфейса, хранящиеся в GIT.  
  
> [!NOTE]
>  Средство таблицы общий интерфейс доступен только в Windows 95 с DCOM версии 1.1 и более поздней версии, Windows 98, Windows NT 4.0 с пакетом обновления 3 и более поздних версий и Windows 2000.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlbase.h  
  
##  <a name="attach"></a>CComGITPtr::Attach  
 Этот метод вызывается для регистрации указателя интерфейса в глобальной таблицы интерфейсов (GIT).  
  
```
HRESULT Attach(T* p) throw();

HRESULT Attach(DWORD dwCookie) throw();
```  
  
### <a name="parameters"></a>Параметры  
 `p`  
 Указатель на интерфейс для добавления GIT.  
  
 `dwCookie`  
 Файл cookie, используемый для идентификации указатель интерфейса.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 В отладочных построениях произойдет ошибка утверждения, если GIT не является допустимым, или в том случае, если файл cookie равен NULL.  
  
##  <a name="ccomgitptr"></a>CComGITPtr::CComGITPtr  
 Конструктор.  
  
```
CComGITPtr() throw();
CComGITPtr(T* p);
CComGITPtr(const CComGITPtr& git);
explicit CComGITPtr(DWORD dwCookie) throw();
CComGITPtr(CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `p`  
 Указатель интерфейса, хранящихся в глобальной таблицы интерфейсов (GIT).  
  
 [in] `git`  
 Ссылка на существующий `CComGITPtr` объекта.  
  
 [in] `dwCookie`  
 Файл cookie, используемый для идентификации указатель интерфейса.  
  
 [in] `rv`  
 Источник `CComGITPtr` объект для перемещения данных из.  
  
### <a name="remarks"></a>Примечания  
 Создает новый `CComGITPtr` объекта, при необходимости с помощью существующего `CComGITPtr` объекта.  
  
 Использование конструктора `rv` является конструктором перемещения. Переместить данные из источника, `rv`, а затем `rv` очищен.  
  
##  <a name="dtor"></a>CComGITPtr:: ~ CComGITPtr  
 Деструктор  
  
```
~CComGITPtr() throw();
```  
  
### <a name="remarks"></a>Примечания  
 Удаляет интерфейс из глобальной таблицы интерфейсов (GIT), с помощью [CComGITPtr::Revoke](#revoke).  
  
##  <a name="copyto"></a>CComGITPtr::CopyTo  
 Этот метод служит для копирования передан указатель интерфейса из глобальной таблицы интерфейсов (GIT).  
  
```
HRESULT CopyTo(T** pp) const throw();
```  
  
### <a name="parameters"></a>Параметры  
 `pp`  
 Указатель, который должен получать интерфейс.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Интерфейс из GIT копируется передан указатель. Указатель должна быть выпущена вызывающим объектом, когда он больше не требуется.  
  
##  <a name="detach"></a>CComGITPtr::Detach  
 Вызов этого метода позволяет отделить интерфейс от `CComGITPtr` объекта.  
  
```
DWORD Detach() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie из `CComGITPtr` объекта.  
  
### <a name="remarks"></a>Примечания  
 Это вызывающий объект должен удалить интерфейс из GIT, с помощью [CComGITPtr::Revoke](#revoke).  
  
##  <a name="getcookie"></a>CComGITPtr::GetCookie  
 Вызовите этот метод для возврата файла cookie из `CComGITPtr` объекта.  
  
```
DWORD GetCookie() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает файл cookie.  
  
### <a name="remarks"></a>Примечания  
 Файл cookie — это переменная, используется для определения интерфейса и его расположение.  
  
##  <a name="m_dwcookie"></a>CComGITPtr::m_dwCookie  
 Файл cookie.  
  
```
DWORD m_dwCookie;
```  
  
### <a name="remarks"></a>Примечания  
 Файл cookie представляет переменную-член используется для определения интерфейса и его расположение.  
  
##  <a name="operator_eq"></a>CComGITPtr::operator =  
 Оператор присваивания.  
  
```
CComGITPtr& operator= (T* p);
CComGITPtr& operator= (const CComGITPtr& git);
CComGITPtr& operator= (DWORD dwCookie);
CComGITPtr& operator= (CComGITPtr&& rv);
```  
  
### <a name="parameters"></a>Параметры  
 [in] `p`  
 Указатель на интерфейс.  
  
 [in] `git`  
 Ссылка на объект `CComGITPtr`.  
  
 [in] `dwCookie`  
 Файл cookie, используемый для идентификации указатель интерфейса.  
  
 [in] `rv`  
 `CComGITPtr` Для перемещения данных из.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает обновленный `CComGITPtr` объекта.  
  
### <a name="remarks"></a>Примечания  
 Присваивает новое значение для `CComGITPtr` объекта, либо из существующего объекта ссылку на общую таблицу интерфейса.  
  
##  <a name="operator_dword"></a>CComGITPtr::operator DWORD  
 Возвращает файл cookie, связанные с `CComGITPtr` объекта.  
  
```  
operator DWORD() const;
```  
  
### <a name="remarks"></a>Примечания  
 Файл cookie — это переменная, используется для определения интерфейса и его расположение.  
  
##  <a name="revoke"></a>CComGITPtr::Revoke  
 Вызовите этот метод, чтобы удалить текущий интерфейс из глобальной таблицы интерфейсов (GIT).  
  
```
HRESULT Revoke() throw();
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает значение S_OK в случае успешного выполнения или значение HRESULT ошибки в случае сбоя.  
  
### <a name="remarks"></a>Примечания  
 Удаляет интерфейс из GIT.  
  
## <a name="see-also"></a>См. также  
 [Упаковщик в режиме свободного потока](../../atl/atl-and-the-free-threaded-marshaler.md)   
 [Доступ к интерфейсам между подразделениями](http://msdn.microsoft.com/library/windows/desktop/ms682353)   
 [Когда следует использовать общую таблицу интерфейса](http://msdn.microsoft.com/library/windows/desktop/ms693729)   
 [Общие сведения о классе](../../atl/atl-class-overview.md)

