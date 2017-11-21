---
title: "Класс CResourceException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CResourceException
- AFXWIN/CResourceException
- AFXWIN/CResourceException::CResourceException
dev_langs: C++
helpviewer_keywords: CResourceException [MFC], CResourceException
ms.assetid: af6ae043-d124-4bfd-b35e-7bb0db67d289
caps.latest.revision: "22"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 497ced5337a44bb0d72be734cfea35a30ead383b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/24/2017
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
 Без дальнейшего уточнения необходимости или возможности.  
  
 Дополнительные сведения об использовании `CResourceException`, см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
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
 Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowResourceException](exception-processing.md#afxthrowresourceexception). Дополнительные сведения об исключениях см. в статье [обработка исключений в MFC](../exception-handling-in-mfc.md).  
  
## <a name="see-also"></a>См. также  
 [CException-класс](cexception-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)


