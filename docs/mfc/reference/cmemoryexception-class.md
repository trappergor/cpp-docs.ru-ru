---
title: Класс CMemoryException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException [MFC], CMemoryException
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 12971af6bed7c04c6f6f214f0b583a4f7e6eb7a1
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366308"
---
# <a name="cmemoryexception-class"></a>Класс CMemoryException
Представляет условие исключения вне памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Создает объект `CMemoryException`.|  
  
## <a name="remarks"></a>Примечания  
 Без дальнейшего уточнения необходимости или возможности. Память исключений автоматически **новый**. При написании собственных функций памяти, с помощью `malloc`для примере, после чего вы несете ответственность за создание исключений в памяти.  
  
 Дополнительные сведения о `CMemoryException`, см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cmemoryexception"></a>  CMemoryException::CMemoryException  
 Создает объект `CMemoryException`.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). в случае нехватки памяти можно успешно эту глобальную функцию, поскольку он создает объект исключения в предварительно выделенной памяти. Дополнительные сведения об обработке исключений см. в статье [исключения](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)



