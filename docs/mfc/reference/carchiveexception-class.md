---
title: Класс CArchiveException | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CArchiveException
- AFX/CArchiveException
- AFX/CArchiveException::CArchiveException
- AFX/CArchiveException::m_cause
- AFX/CArchiveException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CArchiveException [MFC], CArchiveException
- CArchiveException [MFC], m_cause
- CArchiveException [MFC], m_strFileName
ms.assetid: da31a127-e86c-41d1-b0b6-bed0865b1b49
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 2763335a9165c1667160864a40200dcfd44b7f34
ms.sourcegitcommit: c6b095c5f3de7533fd535d679bfee0503e5a1d91
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 06/26/2018
ms.locfileid: "36953104"
---
# <a name="carchiveexception-class"></a>Класс CArchiveException
Представляет условие исключения сериализации  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CArchiveException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchiveException::CArchiveException](#carchiveexception)|Создает объект `CArchiveException`.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CArchiveException::m_cause](#m_cause)|Указывает причину исключения.|  
|[CArchiveException::m_strFileName](#m_strfilename)|Указывает имя файла для данного условия исключения.|  
  
## <a name="remarks"></a>Примечания  
 `CArchiveException` Класс включает это открытый элемент данных, указывающее причину исключения.  
  
 `CArchiveException` создания объектов и вызывается внутри [CArchive](../../mfc/reference/carchive-class.md) функции-члены. Эти объекты в области доступны **ПЕРЕХВАТЫВАТЬ** выражение. Код причины не зависит от операционной системы. Дополнительные сведения об обработке исключений см. в разделе [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CArchiveException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="carchiveexception"></a>  CArchiveException::CArchiveException  
 Создает `CArchiveException` объекта, при сохранении значения *вызвать* в объекте.  
  
```  
CArchiveException(
    int cause = CArchiveException::none,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 *Причина*  
 Переменной перечисляемого типа, указывающее причину создания исключения. Список перечислителей см. в разделе [m_cause](#m_cause) члена данных.  
  
 *lpszArchiveName*  
 Указывает строку, содержащую имя `CArchive` объекта, вызвавшего исключение.  
  
### <a name="remarks"></a>Примечания  
 Можно создать `CArchiveException` объекта в куче и создают его или разрешить глобальную функцию [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception) его дескриптор.  
  
 Не используйте этот конструктор напрямую. Вместо этого вызовите глобальную функцию `AfxThrowArchiveException`.  
  
##  <a name="m_cause"></a>  CArchiveException::m_cause  
 Указывает причину исключения.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член данных — это открытая переменная типа **int**. Его значения определяются `CArchiveException` перечисляемый тип. Перечислители и их значение представлено далее.  
  
- **CArchiveException::none** не возникло ошибок.  
  
- **CArchiveException::genericException** Неизвестная ошибка.  
  
- **CArchiveException::readOnly** попытка записи в архиве, открытом для загрузки.  
  
- **CArchiveException::endOfFile** достигнута конец файла при чтении объекта.  
  
- **CArchiveException::writeOnly** попытка чтения из архиве, открытом для хранения.  
  
- **CArchiveException::badIndex** недопустимый формат файла.  
  
- **CArchiveException::badClass** попытался считать объект в объект неправильного типа.  
  
- **CArchiveException::badSchema** попытался считать объект с помощью другой версии класса.  
  
    > [!NOTE]
    >  Перечислители причины `CArchiveException` отличаются от перечислителей причины `CFileException`.  
  
    > [!NOTE]
    > **CArchiveException::generic** является устаревшим. Используйте **genericException** вместо него. Если **универсального** приложения и построения с/CLR, будет синтаксических ошибок, которые не являются нелегко расшифровать.  
  
##  <a name="m_strfilename"></a>  CArchiveException::m_strFileName  
 Указывает имя файла для данного условия исключения.  
  
```  
CString m_strFileName;  
```  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [CArchive-класс](../../mfc/reference/carchive-class.md)   
 [AfxThrowArchiveException](../../mfc/reference/exception-processing.md#afxthrowarchiveexception)   
 [Обработка исключений](../../mfc/reference/exception-processing.md)

