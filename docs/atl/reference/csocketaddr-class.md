---
title: "Класс CSocketAddr | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSocketAddr
- ATLSOCKET/ATL::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::CSocketAddr
- ATLSOCKET/ATL::CSocketAddr::FindAddr
- ATLSOCKET/ATL::CSocketAddr::FindINET4Addr
- ATLSOCKET/ATL::CSocketAddr::FindINET6Addr
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfo
- ATLSOCKET/ATL::CSocketAddr::GetAddrInfoList
dev_langs:
- C++
helpviewer_keywords:
- CSocketAddr class
ms.assetid: 2fb2d8a7-899e-4a36-a342-cc9f4fcdd68c
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: 33e82acc7b246c1c28eb991c49010f811420094b
ms.contentlocale: ru-ru
ms.lasthandoff: 10/09/2017

---
# <a name="csocketaddr-class"></a>Класс CSocketAddr
Этот класс предоставляет методы для преобразования имен узлов в адреса узлов, поддерживающих форматы IPv4 и IPV6.  
  
## <a name="syntax"></a>Синтаксис  
  
```
class CSocketAddr
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocketAddr::CSocketAddr](#csocketaddr)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSocketAddr::FindAddr](#findaddr)|Вызовите этот метод, чтобы преобразовать указанное имя узла в адрес узла.|  
|[CSocketAddr::FindINET4Addr](#findinet4addr)|Этот метод используется для преобразования имени узла IPv4 адрес узла.|  
|[CSocketAddr::FindINET6Addr](#findinet6addr)|Этот метод используется для преобразования имени узла IPv6 в адрес узла.|  
|[CSocketAddr::GetAddrInfo](#getaddrinfo)|Этот метод возвращает указатель для определенных элементов в **addrinfo** списка.|  
|[CSocketAddr::GetAddrInfoList](#getaddrinfolist)|Вызовите этот метод для возврата указателя на **addrinfo** списка.|  
  
## <a name="remarks"></a>Примечания  
 Этот класс предоставляет IP версии, сокеты независимые подход при поиске сетевых адресов для использования с Windows API-функций и оболочки сокета в библиотеках.  
  
 Члены этого класса, которые используются для поиска сетевых адресов используйте функцию Win32 API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520).  
  
 Этот класс поддерживает оба адреса IPv4 andIPv6 сети.  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** atlsocket.h  
  
##  <a name="csocketaddr"></a>CSocketAddr::CSocketAddr  
 Конструктор.  
  
```
CSocketAddr();
```  
  
### <a name="remarks"></a>Примечания  
 Создает новый `CSocketAddr` объекта и инициализирует связанный список, содержащий ответ сведения об узле.  
  
##  <a name="findaddr"></a>CSocketAddr::FindAddr  
 Вызовите этот метод, чтобы преобразовать указанное имя узла в адрес узла.  
  
```
int FindAddr(
    const char *szHost,
    const char *szPortOrServiceName,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);

int FindAddr(
    const char *szHost,
    int nPortNo,
    int flags,
    int addr_family,
    int sock_type,
    int ai_proto);
```  
  
### <a name="parameters"></a>Параметры  
 `szHost`  
 Имя узла или пунктирную IP-адрес.  
  
 *szPortOrServiceName*  
 Номер порта или имя службы на узле.  
  
 `nPortNo`  
 Номер порта.  
  
 `flags`  
 0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.  
  
 *addr_family*  
 Адрес семейства (например, PF_INET).  
  
 `sock_type`  
 Тип сокета (например, SOCK_STREAM).  
  
 *ai_proto*  
 Протокол (например, IPPROTO_IP или IPPROTO_IPV6).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль, если адрес вычисляется успешно. В неудачи возвращает ненулевой код ошибки Windows Socket. При успешной, вычисляемые адрес, хранится в связанном списке, который можно ссылаться с помощью `CSocketAddr::GetAddrInfoList` и `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Примечания  
 Параметр имени узла может быть в формате IPv4 или IPv6. Этот метод вызывает функцию Win32 API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) для выполнения преобразования.  
  
##  <a name="findinet4addr"></a>CSocketAddr::FindINET4Addr  
 Этот метод используется для преобразования имени узла IPv4 адрес узла.  
  
```
int FindINET4Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Параметры  
 `szHost`  
 Имя узла или пунктирную IP-адрес.  
  
 `nPortNo`  
 Номер порта.  
  
 `flags`  
 0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.  
  
 `sock_type`  
 Тип сокета (например, SOCK_STREAM).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль, если адрес вычисляется успешно. В неудачи возвращает ненулевой код ошибки Windows Socket. При успешной, вычисляемые адрес, хранится в связанном списке, который можно ссылаться с помощью `CSocketAddr::GetAddrInfoList` и `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает функцию Win32 API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) для выполнения преобразования.  
  
##  <a name="findinet6addr"></a>CSocketAddr::FindINET6Addr  
 Этот метод используется для преобразования имени узла IPv6 в адрес узла.  
  
```
int FindINET6Addr(
    const char *szHost,
    int nPortNo,
    int flags,
    int sock_type,);
```  
  
### <a name="parameters"></a>Параметры  
 `szHost`  
 Имя узла или пунктирную IP-адрес.  
  
 `nPortNo`  
 Номер порта.  
  
 `flags`  
 0 или сочетание AI_PASSIVE, AI_CANONNAME или AI_NUMERICHOST.  
  
 `sock_type`  
 Тип сокета (например, SOCK_STREAM).  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает нуль, если адрес вычисляется успешно. В неудачи возвращает ненулевой код ошибки Windows Socket. При успешной, вычисляемые адрес, хранится в связанном списке, который можно ссылаться с помощью `CSocketAddr::GetAddrInfoList` и `CSocketAddr::GetAddrInfo`.  
  
### <a name="remarks"></a>Примечания  
 Этот метод вызывает функцию Win32 API [getaddrinfo](http://msdn.microsoft.com/library/windows/desktop/ms738520) для выполнения преобразования.  
  
##  <a name="getaddrinfo"></a>CSocketAddr::GetAddrInfo  
 Этот метод возвращает указатель для определенных элементов в **addrinfo** списка.  
  
```
addrinfo* const GetAddrInfoint nIndex = 0) const;
```  
  
### <a name="parameters"></a>Параметры  
 `nIndex`  
 Ссылку на определенный элемент в [addrinfo](http://msdn.microsoft.com/library/windows/desktop/ms737530) списка.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Возвращает указатель на **addrinfo** ссылается структура `nIndex` в связанный список, содержащий ответ сведения об узле.  
  
##  <a name="getaddrinfolist"></a>CSocketAddr::GetAddrInfoList  
 Вызовите этот метод для возврата указателя на **addrinfo** списка.  
  
```
addrinfo* const GetAddrInfoList() const;
```  
  
### <a name="return-value"></a>Возвращаемое значение  
 Указатель в связанный список из одного или нескольких `addrinfo` структуры, содержащие ответа сведения об узле. Дополнительные сведения о `addrinfo` структуры, см. в статье «addrinfo» [библиотеки MSDN](http://go.microsoft.com/fwlink/linkid=556)  
  
## <a name="see-also"></a>См. также  
 [Общие сведения о классе](../../atl/atl-class-overview.md)

