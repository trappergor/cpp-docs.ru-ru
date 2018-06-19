---
title: Класс CSimpleException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException [MFC], CSimpleException
- CSimpleException [MFC], GetErrorMessage
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7d04a2f643add489d3302e58a9bde995303ecddd
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
ms.locfileid: "33369929"
---
# <a name="csimpleexception-class"></a>Класс CSimpleException
Этот класс является базовым классом для исключений MFC, связанных с критическими ресурсами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Содержит текст о возникшей ошибке.|  
  
## <a name="remarks"></a>Примечания  
 `CSimpleException` является базовым классом для исключений MFC, критический с точки зрения ресурсов и обрабатывает владения и инициализации сообщения об ошибке. Следующие классы используют `CSimpleException` их базового класса:  
  
|||  
|-|-|  
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запросы на неподдерживаемую операцию|  
|[Класс CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс не найден или не создаваемыми в Windows|  
|[Класс CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает на ресурс не найден|  
|[Класс CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Исключение, которое указывает недопустимый аргумент|  
  
 Поскольку `CSimpleException` является абстрактным базовым классом, нельзя объявлять `CSimpleException` объекта напрямую. Вместо этого необходимо объявить производных объектов, такие как в предыдущей таблице. Если объявляется производный класс используйте предыдущие классы как модель.  
  
 Дополнительные сведения см. в разделе [класса CException](../../mfc/reference/cexception-class.md) раздела и [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="csimpleexception"></a>  CSimpleException::CSimpleException  
 Конструктор.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoDelete`  
 Укажите **TRUE** Если память для `CSimpleException` выделении объекта в куче. Это приведет к `CSimpleException` объект для удаления при **удалить** функция-член вызывается для удаления исключение. Укажите **FALSE** Если `CSimpleException` объект в стеке или — это глобальный объект. В этом случае `CSimpleException` объекта не будут удалены при **удалить** вызвать функцию-член.  
  
### <a name="remarks"></a>Примечания  
 Как правило, никогда не потребуется непосредственно вызвать этот конструктор. Функция, которая создает исключение следует создать экземпляр `CException`-производного класса и вызовите его конструктору, или она должна использовать один из MFC создать исключение функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы создавать предопределенные типа.  
  
##  <a name="geterrormessage"></a>  CSimpleException::GetErrorMessage  
 Вызовите эту функцию-член для предоставления текста о возникшей ошибке.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT  nMaxError,
    PUNIT  pnHelpContext = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lpszError`  
 Указатель на буфер, который получит сообщение об ошибке.  
  
 `nMaxError`  
 Максимальное число символов, может содержаться в буфере, включая **NULL** признака конца.  
  
 `pnHelpContext`  
 Адрес **UINT** , получите идентификатор контекста справки. Если **NULL**, идентификатор не будут возвращены.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае значение 0, если текст сообщения ошибки не доступен.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Обработка исключений](../../mfc/exception-handling-in-mfc.md)



