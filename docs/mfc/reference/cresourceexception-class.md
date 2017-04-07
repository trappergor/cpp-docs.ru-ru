---
title: "Класс CResourceException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs:
- C++
helpviewer_keywords:
- resource allocation exception
- resources [C++], allocating
- resource exceptions
- exceptions, resource
- CResourceException class
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
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
ms.openlocfilehash: 2013a73f91687277df9dd1e6747aba2dd02a4346
ms.lasthandoff: 02/24/2017

---
# <a name="cresourceexception-class"></a>Класс CResourceException
Генерируется, когда Windows не может найти или выбрать запрошенный ресурс.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CResourceException : public CSimpleException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CResourceException::CResourceException](#cresourceexception)|Создает объект `CResourceException`.|  
  
## <a name="remarks"></a>Примечания  
 Без дальнейшего уточнения необходимые или невозможна.  
  
 Дополнительные сведения об использовании `CResourceException`, см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CResourceException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afxwin.h  
  
##  <a name="cresourceexception"></a>CResourceException::CResourceException  
 Создает объект `CResourceException`.  
  
```  
CResourceException();
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор, непосредственно, но вместо этого вызовите глобальную функцию [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Дополнительные сведения об исключениях см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)



