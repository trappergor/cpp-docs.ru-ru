---
title: "Класс CInternetException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: bb94e24657d16b2a3eda3a770c2b6ae734c6006f
ms.openlocfilehash: 1831f868b7388cbc6382e26fca92280c3b880276
ms.contentlocale: ru-ru
ms.lasthandoff: 04/12/2017

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
 `CInternetException` Класс содержит два открытые члены данных: один содержит код ошибки, связанный с исключением, а другое содержит идентификатор контекста для Интернет-приложения, с которым связана ошибка.  
  
 Дополнительные сведения об идентификаторах контекста для веб-приложений см. в статье [Интернет программирование с использованием WinInet](../../mfc/win32-internet-extensions-wininet.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CInternetException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxinet.h  
  
##  <a name="cinternetexception"></a>CInternetException::CInternetException  
 Эта функция-член вызывается, когда `CInternetException` создан объект.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Параметры  
 `dwError`  
 Ошибки, вызвавшей исключение.  
  
### <a name="remarks"></a>Примечания  
 Чтобы создать CInternetException, вызовите глобальную функцию MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
##  <a name="m_dwcontext"></a>CInternetException::m_dwContext  
 Значение контекста, связанное с связанные Интернет-операции.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста изначально указывается в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и передаются по MFC, позволяющий [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- и [классе CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы. Можно переопределить поведение по умолчанию и назначить любой `dwContext` параметра значение по своему выбору. `dwContext`связан с любой операции данного объекта. `dwContext`Определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>CInternetException::m_dwError  
 Ошибки, вызвавшей исключение.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой ошибки может быть системой код ошибки, содержится в WINERROR. H или код ошибки из WININET. З.  
  
 Список кодов ошибок Win32 см. в разделе [коды ошибок](http://msdn.microsoft.com/library/windows/desktop/ms681381). Список ошибок сообщения, относящиеся к Интернету см. в разделе. Оба раздела находятся в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CException](../../mfc/reference/cexception-class.md)

