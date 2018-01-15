---
title: "Класс COleDispatchException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleDispatchException
- AFXDISP/COleDispatchException
- AFXDISP/COleDispatchException::m_dwHelpContext
- AFXDISP/COleDispatchException::m_strDescription
- AFXDISP/COleDispatchException::m_strHelpFile
- AFXDISP/COleDispatchException::m_strSource
- AFXDISP/COleDispatchException::m_wCode
dev_langs: C++
helpviewer_keywords:
- COleDispatchException [MFC], m_dwHelpContext
- COleDispatchException [MFC], m_strDescription
- COleDispatchException [MFC], m_strHelpFile
- COleDispatchException [MFC], m_strSource
- COleDispatchException [MFC], m_wCode
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d90c59e4f85c871c113e51063ef1d50997bb508b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coledispatchexception-class"></a>Класс COleDispatchException
Обрабатывает исключения, относящиеся к интерфейсу OLE `IDispatch` и являющиеся ключевой частью OLE-автоматизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Контекст справки для ошибки.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|Ошибка словесное описание.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Файл для использования с справки `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#m_strsource)|Приложения, создавшего исключение.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-код ошибки.|  
  
## <a name="remarks"></a>Примечания  
 Как и другие классы исключений производными от `CException` базового класса, `COleDispatchException` может использоваться с **THROW**, `THROW_LAST`, **ПОВТОРИТЕ**, **ПЕРЕХВАТЫВАТЬ**, `AND_CATCH`, и `END_CATCH` макросы.  
  
 В общем случае следует вызывать [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) для создания и вызова `COleDispatchException` объекта.  
  
 Дополнительные сведения об исключениях см. в статьях [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 Идентифицирует контекст справки в справке вашего приложения (. Файл HLP).  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член, установленное с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 Содержит описание устные ошибки, например «Диск заполнен».  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член, установленное с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 Платформа заполняет эту строку с именем в файле справки.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>COleDispatchException::m_strSource  
 Платформа заполняет эту строку с именем приложения, создавшего исключение.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_wcode"></a>COleDispatchException::m_wCode  
 Содержит код ошибки, относящихся к конкретному приложению.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член, установленное с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда возникает исключение.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)   
 [Класс COleException](../../mfc/reference/coleexception-class.md)
