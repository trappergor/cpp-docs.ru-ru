---
title: "Класс COleException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleException
- AFXDISP/COleException
- AFXDISP/COleException::Process
- AFXDISP/COleException::m_sc
dev_langs: C++
helpviewer_keywords:
- COleException [MFC], Process
- COleException [MFC], m_sc
ms.assetid: 2571e9fe-26cc-42f0-9ad9-8ad5b4311ec1
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7e895e893c6032a8f8d7db0549f872c82cd0d9b5
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="coleexception-class"></a>Класс COleException
Представляет исключительное условие, связанное с операцией OLE.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class COleException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleException::Process](#process)|Преобразует перехваченного исключения в кодом возврата OLE.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[COleException::m_sc](#m_sc)|Содержит код состояния, указывающее причину создания исключения.|  
  
## <a name="remarks"></a>Примечания  
 `COleException` Класс включает это открытый элемент данных, содержащий код состояния, указывающее причину создания исключения.  
  
 В общем случае не следует создавать `COleException` объекта напрямую; вместо этого следует вызывать [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Дополнительные сведения об исключениях см. в статьях [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md) и [исключений: исключения OLE](../../mfc/exceptions-ole-exceptions.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `COleException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxdisp.h  
  
##  <a name="m_sc"></a>COleException::m_sc  
 Этот элемент данных содержит код состояния OLE, указывающее причину создания исключения.  
  
```  
SCODE m_sc;  
```  
  
### <a name="remarks"></a>Примечания  
 Значение этой переменной устанавливается [AfxThrowOleException](exception-processing.md#afxthrowoleexception).  
  
 Дополнительные сведения о `SCODE`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCOleContainer#22](../../mfc/codesnippet/cpp/coleexception-class_1.cpp)]  
  
##  <a name="process"></a>COleException::Process  
 Вызовите **процесс** функция-член для преобразования в код состояния OLE перехваченного исключения.  
  
```  
static SCODE PASCAL Process(const CException* pAnyException);
```  
  
### <a name="parameters"></a>Параметры  
 *pAnyException*  
 Указатель перехваченного исключения.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Код состояния OLE.  
  
### <a name="remarks"></a>Примечания  
  
> [!NOTE]
>  Эта функция представляет **статических**.  
  
 Дополнительные сведения о `SCODE`, в разделе [структуры из кодов ошибок модели COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) в Windows SDK.  
  
### <a name="example"></a>Пример  
  Далее приведен пример [COleDispatchDriver::CreateDispatch](../../mfc/reference/coledispatchdriver-class.md#createdispatch).  
  
## <a name="see-also"></a>См. также  
 [Пример MFC CALCDRIV](../../visual-cpp-samples.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)



