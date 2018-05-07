---
title: Класс CNotSupportedException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 510f9db4a7e5688df76baafa868846fd1614f584
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cnotsupportedexception-class"></a>Класс CNotSupportedException
Представляет исключение, являющееся результатом запроса неподдерживаемой возможности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Создает объект `CNotSupportedException`.|  
  
## <a name="remarks"></a>Примечания  
 Без дальнейшего уточнения необходимости или возможности.  
  
 Дополнительные сведения об использовании `CNotSupportedException`, см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cnotsupportedexception"></a>  CNotSupportedException::CNotSupportedException  
 Создает объект `CNotSupportedException`.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Дополнительные сведения об обработке исключений см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)


