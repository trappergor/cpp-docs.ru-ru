---
title: "Класс CNotSupportedException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CNotSupportedException
- AFX/CNotSupportedException
- AFX/CNotSupportedException::CNotSupportedException
dev_langs: C++
helpviewer_keywords: CNotSupportedException [MFC], CNotSupportedException
ms.assetid: e517391b-eb94-4c39-ae32-87b45bf7d624
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 55416272671d9c03422fcb74ec03ecc02ed671ee
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
 Без дальнейшего уточнения необходимости или возможности.  
  
 Дополнительные сведения об использовании `CNotSupportedException`, см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
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
 Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowNotSupportedException](exception-processing.md#afxthrownotsupportedexception). Дополнительные сведения об обработке исключений см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)


