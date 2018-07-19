---
title: Класс CInternetException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
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
- CInternetException [MFC], CInternetException
- CInternetException [MFC], m_dwContext
- CInternetException [MFC], m_dwError
ms.assetid: 44fb3cbe-523e-4754-8843-a77909990b14
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 6db83d88eec06ce21258ed751c5e1b232f696836
ms.sourcegitcommit: f1b051abb1de3fe96350be0563aaf4e960da13c3
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/27/2018
ms.locfileid: "37037893"
---
# <a name="cinternetexception-class"></a>Класс CInternetException
Представляет условие исключения, касающееся интернет-операции.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInternetException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CInternetException::CInternetException](#cinternetexception)|Создает объект `CInternetException`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
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
  
##  <a name="cinternetexception"></a>  CInternetException::CInternetException  
 Эта функция-член вызывается, когда `CInternetException` создан объект.  
  
```  
CInternetException(DWORD dwError);
```  
  
### <a name="parameters"></a>Параметры  
 *dwError*  
 Ошибки, вызвавшей исключение.  
  
### <a name="remarks"></a>Примечания  
 Чтобы создать CInternetException, вызовите глобальную функцию MFC [AfxThrowInternetException](internet-url-parsing-globals.md#afxthrowinternetexception).  
  
##  <a name="m_dwcontext"></a>  CInternetException::m_dwContext  
 Значение контекста, связанное с связанные Интернет-операции.  
  
```  
DWORD_PTR m_dwContext;  
```  
  
### <a name="remarks"></a>Примечания  
 Идентификатор контекста изначально указывается в [CInternetSession](../../mfc/reference/cinternetsession-class.md) и передаются по MFC, позволяющий [CInternetConnection](../../mfc/reference/cinternetconnection-class.md)- и [классе CInternetFile](../../mfc/reference/cinternetfile-class.md)-производные классы. Можно переопределить поведение по умолчанию и назначить любой *dwContext* параметра значение по своему выбору. *dwContext* связан с любой операции данного объекта. *dwContext* определяет сведения о состоянии операции, возвращаемые [CInternetSession::OnStatusCallback](../../mfc/reference/cinternetsession-class.md#onstatuscallback).  
  
##  <a name="m_dwerror"></a>  CInternetException::m_dwError  
 Ошибки, вызвавшей исключение.  
  
```  
DWORD m_dwError;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой ошибки может быть системой код ошибки, содержится в WINERROR. H или код ошибки из WININET. З.  
  
 Список кодов ошибок Win32 см. в разделе [коды ошибок](http://msdn.microsoft.com/library/windows/desktop/ms681381). Список ошибок сообщения, относящиеся к Интернету см. в разделе. Оба раздела, в Windows SDK.  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CException](../../mfc/reference/cexception-class.md)
