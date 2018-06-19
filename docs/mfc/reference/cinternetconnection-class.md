---
title: Класс CInternetConnection | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CInternetConnection [MFC], CInternetConnection
- CInternetConnection [MFC], GetContext
- CInternetConnection [MFC], GetServerName
- CInternetConnection [MFC], GetSession
ms.assetid: 62a5d1c3-8471-4e36-a064-48831829b2a7
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 07b269afce3ec0c3ef60e6cc37782fdea18260cf
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366682"
---
# <a name="cinternetconnection-class"></a>Класс CInternetConnection
Управление подключением к интернет-серверу.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetConnection : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::CInternetConnection](#cinternetconnection)|Создает объект `CInternetConnection`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::GetContext](#getcontext)|Возвращает идентификатор контекста для объекта соединения.|  
|[CInternetConnection::GetServerName](#getservername)|Возвращает имя сервера, связанного с соединением.|  
|[CInternetConnection::GetSession](#getsession)|Возвращает указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, связанного с соединением.|  
  
### <a name="public-operators"></a>Открытые операторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetConnection::operator HINTERNET](#operator_hinternet)|Дескриптор для Интернет-сеанс.|  
  
## <a name="remarks"></a>Примечания  
 Это базовый класс для классов MFC [классе CFtpConnection](../../mfc/reference/cftpconnection-class.md), [CHttpConnection](../../mfc/reference/chttpconnection-class.md), и [CGopherConnection](../../mfc/reference/cgopherconnection-class.md). Каждый из этих классов предоставляет дополнительные функциональные возможности для взаимодействия с на соответствующий сервер gopher, HTTP или FTP.  
  
 Для взаимодействия непосредственно с веб-сервером, необходимо иметь [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта и `CInternetConnection` объекта.  
  
 Дополнительные сведения о как WinInet классов см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CInternetConnection`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cinternetconnection"></a>  CInternetConnection::CInternetConnection  
 Эта функция-член вызывается, когда `CInternetConnection` создан объект.  
  
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
 Число, определяющее порт Интернета для этого подключения.  
  
 `dwContext`  
 Идентификатор контекста для `CInternetConnection` объекта. В разделе **примечания** Дополнительные сведения о `dwContext`.  
  
### <a name="remarks"></a>Примечания  
 Невозможно вызвать `CInternetConnection` самостоятельно; вместо этого необходимо вызвать [CInternetSession](../../mfc/reference/cinternetsession-class.md) функции-члена для типа соединения, которым требуется установить:  
  
- [CInternetSession::GetFtpConnection](../../mfc/reference/cinternetsession-class.md#getftpconnection)  
  
- [CInternetSession::GetHttpConnection](../../mfc/reference/cinternetsession-class.md#gethttpconnection)  
  
- [CInternetSession::GetGopherConnection](../../mfc/reference/cinternetsession-class.md#getgopherconnection)  
  
 Значение по умолчанию для `dwContext` отправленных MFC, позволяющий `CInternetConnection`-производный объект от [CInternetSession](../../mfc/reference/cinternetsession-class.md) объекта, который создан **Интернет-соединение**-производного объекта. Значение по умолчанию имеет значение 1; Тем не менее, можно явно назначить идентификатора контекста в [CInternetSession](../../mfc/reference/cinternetsession-class.md#cinternetsession) конструктор для соединения. Объект, а вся работа, она будет связана с этим идентификатором контекста. Идентификатор контекста возвращается [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback) показывают состояние для объекта, с помощью которого определяется. См. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о идентификатора контекста.  
  
##  <a name="getcontext"></a>  CInternetConnection::GetContext  
 Вызовите эту функцию-член для получения идентификатора контекста для данного сеанса.  
  
```  
DWORD_PTR GetContext() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Идентификатор контекста, назначенный веб-приложения  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста изначально указывается в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и распространение на `CInternetConnection`- и [классе CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы, в том случае, если не указано иначе, в вызове функции, которая открывает соединение. Идентификатор контекста, связанного с любой операции данного объекта и определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
 Дополнительные сведения о том, как **GetContext** работает с другими классами WinInet, чтобы предоставить сведения о состоянии пользователя, см. в статье [первые шаги в Интернете: WinInet](../../mfc/wininet-basics.md) Дополнительные сведения о контексте идентификатор.  
  
##  <a name="getservername"></a>  CInternetConnection::GetServerName  
 Вызовите эту функцию-член для получения имени сервера, связанного с этим подключением Интернета.  
  
```  
CString GetServerName() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Имя сервера работает этот объект.  
  
##  <a name="getsession"></a>  CInternetConnection::GetSession  
 Вызовите эту функцию-член для получения указателя на `CInternetSession` объект, связанный с данным соединением.  
  
```  
CInternetSession* GetSession() const;  
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель на [CInternetSession](../../mfc/reference/cinternetsession-class.md) объект, связанный с этим объектом подключения Интернета.  
  
##  <a name="operator_hinternet"></a>  CInternetConnection::operator HINTERNET  
 Этот оператор используется для получения дескриптора уровень API для текущего сеанса Интернет.  
  
```  
operator HINTERNET() const;  
```  
  
## <a name="see-also"></a>См. также  
 [CObject-класс](../../mfc/reference/cobject-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



