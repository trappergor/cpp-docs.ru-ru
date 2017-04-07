---
title: "Класс COleDispatchException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
dev_langs:
- C++
helpviewer_keywords:
- COleDispatchException class
- Automation, exceptions
- exceptions, OLE
- OLE exceptions, to IDispatch interface
ms.assetid: 0e95c8be-e21a-490c-99ec-181c6a9a26d0
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
ms.openlocfilehash: 0071e57b6c8f6bec73712186e8ff8baa9bfcc165
ms.lasthandoff: 02/24/2017

---
# <a name="coledispatchexception-class"></a>Класс COleDispatchException
Обрабатывает исключения, относящиеся к интерфейсу OLE `IDispatch` и являющиеся ключевой частью OLE-автоматизации.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleDispatchException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleDispatchException::m_dwHelpContext](#m_dwhelpcontext)|Контекст справки для ошибки.|  
|[COleDispatchException::m_strDescription](#m_strdescription)|Ошибка словесное описание.|  
|[COleDispatchException::m_strHelpFile](#m_strhelpfile)|Файл для использования с справки `m_dwHelpContext`.|  
|[COleDispatchException::m_strSource](#m_strsource)|Приложение, вызвавшее исключение.|  
|[COleDispatchException::m_wCode](#m_wcode)|`IDispatch`-код ошибки.|  
  
## <a name="remarks"></a>Примечания  
 Как и другие классы исключений, производные от `CException` базового класса, `COleDispatchException` может использоваться с **исключение**, `THROW_LAST`, **попробуйте**, **CATCH**, `AND_CATCH`, и `END_CATCH` макросы.  
  
 В общем случае следует вызывать [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) Чтобы создать и вызвать `COleDispatchException` объекта.  
  
 Дополнительные сведения об исключениях см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключения: OLE исключения](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleDispatchException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="m_dwhelpcontext"></a>COleDispatchException::m_dwHelpContext  
 Определяет контекст справки в справке приложения (. Файл HLP).  
  
```  
DWORD m_dwHelpContext;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда создается исключение.  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strdescription"></a>COleDispatchException::m_strDescription  
 Содержит описание устные ошибки, например «Диск заполнен».  
  
```  
CString m_strDescription;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда создается исключение.  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_strhelpfile"></a>COleDispatchException::m_strHelpFile  
 Платформа заполняет эту строку с именем в файле справки.  
  
```  
CString m_strHelpFile;  
```  
  
##  <a name="m_strsource"></a>COleDispatchException::m_strSource  
 Автоматически заполняются в этой строке на имя приложения, создавшего исключение.  
  
```  
CString m_strSource;  
```  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
##  <a name="m_wcode"></a>COleDispatchException::m_wCode  
 Содержит код ошибки, присущие приложению.  
  
```  
WORD m_wCode;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член задан с помощью функции [AfxThrowOleDispatchException](exception-processing.md#afxthrowoledispatchexception) когда создается исключение.  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс COleDispatchDriver](../../mfc/reference/coledispatchdriver-class.md)   
 [Класс COleException](../../mfc/reference/coleexception-class.md)

