---
title: Класс CInvalidArgException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CInvalidArgException
- AFX/CInvalidArgException
- AFX/CInvalidArgException::CInvalidArgException
dev_langs:
- C++
helpviewer_keywords:
- CInvalidArgException [MFC], CInvalidArgException
ms.assetid: e43d7c67-1157-47f8-817a-804083e8186e
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a71802a4544ae238474a0747d879d29c69f6ba19
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33366753"
---
# <a name="cinvalidargexception-class"></a>Класс CInvalidArgException
Этот класс представляет условие исключения, связанного с недопустимым аргументом.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CInvalidArgException : public CSimpleException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CInvalidArgException::CInvalidArgException](#cinvalidargexception)|Конструктор.|  
  
## <a name="remarks"></a>Примечания  
 Объект `CInvalidArgException` объект представляет условие исключения недопустимого аргумента.  
  
 Дополнительные сведения об обработке исключений см. в разделе [класса CException](../../mfc/reference/cexception-class.md) раздела и [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 [CSimpleException](../../mfc/reference/csimpleexception-class.md)  
  
 `CInvalidArgException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cinvalidargexception"></a>  CInvalidArgException::CInvalidArgException  
 Конструктор.  
  
```  
CInvalidArgException();
```  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор напрямую. Вызовите глобальную функцию **AfxThrowInvalidArgException**.  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Класс CSimpleException](../../mfc/reference/csimpleexception-class.md)
