---
title: "Класс CSimpleException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleException
- AFX/CSimpleException
- AFX/CSimpleException::CSimpleException
- AFX/CSimpleException::GetErrorMessage
dev_langs:
- C++
helpviewer_keywords:
- CSimpleException class
ms.assetid: be0eb8ef-e5b9-47d6-b0fb-efaff2d1e666
caps.latest.revision: 19
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5612d76a2351b9898b8ffe082844686d21fcd7a0
ms.lasthandoff: 02/24/2017

---
# <a name="csimpleexception-class"></a>Класс CSimpleException
Этот класс является базовым классом для исключений MFC, связанных с критическими ресурсами.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CSimpleException : public CException  
```  
  
## <a name="members"></a>Члены  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleException::CSimpleException](#csimpleexception)|Конструктор.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CSimpleException::GetErrorMessage](#geterrormessage)|Предоставляет сведения о возникшей ошибке.|  
  
## <a name="remarks"></a>Примечания  
 `CSimpleException`является базовым классом для исключений ресурсов с точки зрения MFC и обрабатывает владения и инициализации сообщения об ошибке. Следующие классы используют `CSimpleException` как базовый класс:  
  
|||  
|-|-|  
|[Класс CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[Класс CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запросы неподдерживаемая операция|  
|[Класс CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows, не найден или не создаваемый объект|  
|[Класс CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает на ресурс не найден|  
|[Класс CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Исключение, которое указывает недопустимый аргумент|  
  
 Поскольку `CSimpleException` является абстрактным базовым классом, невозможно объявить `CSimpleException` напрямую. Вместо этого необходимо объявить производных объектов, например, в предыдущей таблице. При объявлении производного класса используйте предыдущие классы как модель.  
  
 Дополнительные сведения см. в разделе [класса CException](../../mfc/reference/cexception-class.md) раздела и [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CSimpleException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="csimpleexception"></a>CSimpleException::CSimpleException  
 Конструктор.  
  
```  
CSimpleException();  
explicit CSimpleException(BOOL bAutoDelete);
```  
  
### <a name="parameters"></a>Параметры  
 `bAutoDelete`  
 Укажите **TRUE** Если память для `CSimpleException` объект выделен в куче. Это приведет к `CSimpleException` объект для удаления при **удаление** функция-член вызывается для удаления исключения. Укажите **FALSE** Если `CSimpleException` объект в стеке или — это глобальный объект. В этом случае `CSimpleException` объект не будет удален при **удаление** вызывается функция-член.  
  
### <a name="remarks"></a>Примечания  
 Напрямую вызывать этот конструктор обычно никогда не потребуется. Функция, которая создает исключение должно создать экземпляр `CException`-производный класс и вызывать его конструктор, или воспользуйтесь одним из MFC вызывает функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы создавать предопределенные типа.  
  
##  <a name="geterrormessage"></a>CSimpleException::GetErrorMessage  
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
 Максимальное количество символов может содержаться в буфере, включая **NULL** признака конца.  
  
 `pnHelpContext`  
 Адрес **UINT** , принимающий идентификатор контекста справки Если **NULL**, идентификатор не будет возвращено.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Ненулевое значение, если функция выполнена успешно; в противном случае — 0, если текст сообщения ошибки не доступен.  
  
### <a name="remarks"></a>Примечания  
 Дополнительные сведения см. в разделе [CException::GetErrorMessage](../../mfc/reference/cfileexception-class.md#geterrormessage).  
  
## <a name="see-also"></a>См. также  
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Обработка исключений](../../mfc/exception-handling-in-mfc.md)




