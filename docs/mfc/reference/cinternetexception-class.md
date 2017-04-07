---
title: "Класс CInternetException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CInternetException
- AFXINET/CInternetException
- AFXINET/CInternetException::CInternetException
- AFXINET/CInternetException::m_dwContext
- AFXINET/CInternetException::m_dwError
dev_langs:
- C++
helpviewer_keywords:
- exception handling, Internet operations
- exceptions, Internet
- CInternetException class
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
caps.latest.revision: 22
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
translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a128095cfc443f0ea8de4cb4028b903929a83f47
ms.lasthandoff: 02/24/2017

---
# <a name="cinternetexception-class"></a>Класс CInternetException
Представляет условие исключения, касающееся интернет-операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Создает объект `CInternetException`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInternetException::m_dwContext](#m_dwcontext)|Значение контекста, связанного с операцией, которая вызвала исключение.|  
|[CInternetException::m_dwError](#m_dwerror)|Ошибки, вызвавшей исключение.|  
  
## <a name="remarks"></a>Примечания  
 `CInternetException` Класс включает две открытые члены данных: один содержит код ошибки, связанный с исключением, а другое содержит идентификатор контекста для веб-приложение, связанное с ошибкой.  
  
 Дополнительные сведения об идентификаторах контекста для веб-приложений см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Эта функция-член вызывается `CInternetException` создается объект.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Параметры  
 `dwError`  
 Ошибки, вызвавшей исключение.  
  
### <a name="remarks"></a>Примечания  
 Для вызова CInternetException, вызовите глобальную функцию MFC [AfxThrowInternetException](http://msdn.microsoft.com/library/c9645b10-9541-48b2-8b0c-94ca33fed3cb).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 Значение контекста, связанное с связанных Интернет-операции.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста первоначально заданным в параметре [CInternetSession](../../mfc/reference/cinternetsession-class.md) и передаются по MFC для [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- и [CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы. Можно переопределить это поведение по умолчанию и назначить любой `dwContext` параметра значение по своему выбору. `dwContext`связан с любой операции данного объекта. `dwContext`Определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 Ошибки, вызвавшей исключение.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой ошибки может быть системы код ошибки, в WINERROR. H, или значение ошибки из WININET. З.  
  
 Список кодов ошибок Win32 см. в разделе [коды ошибок](http://msdn.microsoft.com/library/windows/desktop/ms681381). Список Интернет конкретных сообщений об ошибках см. Оба разделов [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)

