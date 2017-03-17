---
title: "Класс COleException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs:
- C++
helpviewer_keywords:
- COleException class
- exceptions, OLE
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 059c92c8dc8796cf103cc02533ba5f3526720249
ms.lasthandoff: 02/24/2017

---
# <a name="coleexception-class"></a>Класс COleException
Представляет исключительное условие, связанное с операцией OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleException::Process](#process)|Преобразует перехваченного исключения в код возврата OLE.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Содержит код состояния, который указывает причину возникновения исключения.|  
  
## <a name="remarks"></a>Примечания  
 `COleException` Класс включает открытого члена данных, содержащий код состояния, указывающий причину исключения.  
  
 В общем случае не следует создавать `COleException` объекта напрямую; вместо этого следует вызвать [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Дополнительные сведения об исключениях см. в статьях [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключения: OLE исключения](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 Этот член данных содержит код состояния OLE, которое указывает причину возникновения исключения.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой переменной устанавливается [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Дополнительные сведения о `SCODE`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer&#22;](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 Вызов **процесс** функции-члена для преобразования в код состояния OLE перехваченное исключение.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Параметры  
 *pAnyException*  
 Указатель перехваченное исключение.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код состояния OLE.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция является **статических**.  
  
 Дополнительные сведения о `SCODE`, в разделе [структура кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Пример  
  В примере показано [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)




