---
title: "Класс CNotSupportedException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs:
- C++
helpviewer_keywords:
- CNotSupportedException class
- unsupported features
- exceptions, not supported
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: 20
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 6cb66448d0dadaf1f70c3606bc1b9027bd217a38
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cnotsupportedexception-class"></a>Класс CNotSupportedException
Представляет исключение, являющееся результатом запроса неподдерживаемой возможности.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CNotSupportedException : public CSimpleException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CNotSupportedException::CNotSupportedException](#cnotsupportedexception)|Создает объект `CNotSupportedException`.|  
  
## <a name="remarks"></a>Примечания  
 Без дальнейшего уточнения необходимые или невозможна.  
  
 Дополнительные сведения об использовании `CNotSupportedException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CNotSupportedException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cnotsupportedexception"></a>CNotSupportedException::CNotSupportedException  
 Создает объект `CNotSupportedException`.  
  
```  
CNotSupportedException();
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор, непосредственно, но вместо этого вызовите глобальную функцию [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Дополнительные сведения об обработке исключений см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)



