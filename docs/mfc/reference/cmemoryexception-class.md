---
title: "Класс CMemoryException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMemoryException
- AFX/CMemoryException
- AFX/CMemoryException::CMemoryException
dev_langs:
- C++
helpviewer_keywords:
- CMemoryException class
- memory exceptions
- exceptions, memory type
- C++ exception handling, memory
- memory, exception handling
ms.assetid: 9af0ed57-d12a-45ca-82b5-c910a60f7edf
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
ms.openlocfilehash: 87be1b16d546791d24bbffa62207ec9ccb350139
ms.contentlocale: ru-ru
ms.lasthandoff: 02/24/2017

---
# <a name="cmemoryexception-class"></a>Класс CMemoryException
Представляет условие исключения вне памяти.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CMemoryException : public CSimpleException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CMemoryException::CMemoryException](#cmemoryexception)|Создает объект `CMemoryException`.|  
  
## <a name="remarks"></a>Примечания  
 Без дальнейшего уточнения необходимые или невозможна. Память исключений автоматически **новый**. При написании собственных функций памяти с помощью `malloc`, для примера, после чего отвечают за создание исключений в памяти.  
  
 Дополнительные сведения о `CMemoryException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CMemoryException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cmemoryexception"></a>CMemoryException::CMemoryException  
 Создает объект `CMemoryException`.  
  
```  
CMemoryException();  
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор, непосредственно, но вместо этого вызовите глобальную функцию [AfxThrowMemoryException](exception-processing.md#afxthrowmemoryexception). в случае нехватки памяти можно успешно эту глобальную функцию, поскольку он создает объект исключения в предварительно выделенной памяти. Дополнительные сведения об обработке исключений см. в статье [исключения](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)




