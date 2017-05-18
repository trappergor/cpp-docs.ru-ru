---
title: "Класс CInternetConnection | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetConnection
- AFXINET/CInternetConnection
- AFXINET/CInternetConnection::CInternetConnection
- AFXINET/CInternetConnection::GetContext
- AFXINET/CInternetConnection::GetServerName
- AFXINET/CInternetConnection::GetSession
dev_langs:
- C++
helpviewer_keywords:
- asynchronous connections
- CInternetConnection class
- Internet connections
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
caps.latest.revision: 21
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
ms.openlocfilehash: 7f99562e0c6103fc3f46a7fe28f9d2f2efff0a01
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetconnection-class"></a>Класс CInternetConnection
Управление подключением к интернет-серверу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Создает объект `CInternetConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Возвращает идентификатор контекста для данного объекта подключения.|  
|[CInternetConnection::GetServerName](#getservername)|Возвращает имя сервера, связанного с подключением.|  
|[CInternetConnection::GetSession](#getsession)|Возвращает указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объект, связанный с подключением.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Дескриптор для Интернет-сеанс.|  
  
## <a name="remarks"></a>Примечания  
 Это базовый класс для классов MFC [CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Каждый из этих классов предоставляет дополнительные возможности для связи с соответствующим сервером FTP, HTTP и gopher.  
  
 Для взаимодействия непосредственно с веб-сервером, необходимо иметь [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта и `CInternetConnection` объекта.  
  
 Дополнительные сведения о как WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cinternetconnection"></a>CInternetConnection::CInternetConnection  
 Эта функция-член вызывается `CInternetConnection` создается объект.  
  
```  
CInternetConnection(
    CInternetSession* pSession,  
    LPCTSTR pstrServer,  
    INTERNET_PORT nPort = INTERNET_INVALID_PORT_NUMBER,  
    DWORD_PTR dwContext = 1);
```  
  
### <a name="parameters"></a>Параметры  
 `pSession`  
 Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта.  
  
 `pstrServer`  
 Указатель на строку, содержащую имя сервера.  
  
 `nPort`  
 Число, идентифицирующее порт Интернета для данного подключения.  
  
 `dwContext`  
 Идентификатор контекста для `CInternetConnection` объекта. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="remarks"></a>Примечания  
 Никогда не вызывать `CInternetConnection` самостоятельно; вместо этого необходимо вызвать [CInternetSession](../../mfc/reference/cinternetsession-class.md) функции-члена для типа подключения требуется установить:  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 Значение по умолчанию для `dwContext` отправленных MFC для `CInternetConnection`-производный объект от [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан **Интернет-соединение**-производный объект. По умолчанию используется значение 1; Однако можно явно назначить идентификатор определенного контекста в [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) конструктор для подключения. Объект, а вся работа, она будет связан с этим идентификатором контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) для предоставления состояния объекта, с помощью которого определяется. См. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="getcontext"></a>CInternetConnection::GetContext  
 Вызовите эту функцию-член для получения идентификатора контекста для данного сеанса.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста, назначенный приложения  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста первоначально заданным в параметре [CInternetSession](../../mfc/reference/cinternetsession-class.md) и распространение на `CInternetConnection`- и [CInternetFile](../../mfc/reference/cinternetfile-class.md)-производных классов, если не указано иначе, в вызове функции, которая открывает соединение. Идентификатор контекста связано с любой операции данного объекта и определяет возвращаемые сведения о состоянии операции [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Дополнительные сведения о том, как **GetContext** работает с другими классами WinInet, чтобы предоставить сведения о состоянии пользователя, см. в статье [Интернет первые шаги: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="getservername"></a>CInternetConnection::GetServerName  
 Вызовите эту функцию-член для получения имени сервера, связанного с этим подключением Интернета.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя сервера, внутри которого работает данный объект подключения.  
  
##  <a name="getsession"></a>CInternetConnection::GetSession  
 Вызов этой функции-члена для получения указателя на `CInternetSession` объекта, который связан с данным соединением.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объект, связанный с объектом подключения Интернета.  
  
##  <a name="operator_hinternet"></a>CInternetConnection::operator HINTERNET  
 Этот оператор используется для получения дескриптора уровня API для текущего сеанса Internet.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




