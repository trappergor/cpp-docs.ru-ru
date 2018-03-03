---
title: "Класс CFileException | Документы Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileException
- AFX/CFileException
- AFX/CFileException::CFileException
- AFX/CFileException::ErrnoToException
- AFX/CFileException::GetErrorMessage
- AFX/CFileException::OsErrorToException
- AFX/CFileException::ThrowErrno
- AFX/CFileException::ThrowOsError
- AFX/CFileException::m_cause
- AFX/CFileException::m_lOsError
- AFX/CFileException::m_strFileName
dev_langs:
- C++
helpviewer_keywords:
- CFileException [MFC], CFileException
- CFileException [MFC], ErrnoToException
- CFileException [MFC], GetErrorMessage
- CFileException [MFC], OsErrorToException
- CFileException [MFC], ThrowErrno
- CFileException [MFC], ThrowOsError
- CFileException [MFC], m_cause
- CFileException [MFC], m_lOsError
- CFileException [MFC], m_strFileName
ms.assetid: f6491bb9-bfbc-42fd-a952-b33f9b62323f
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: a46741e2f2896fbed16c052ff9fc340d9394a2e6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 12/21/2017
---
# <a name="cfileexception-class"></a>Класс CFileException
Представляет состояние, связанное с файлом исключения.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class CFileException : public CException  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileException::CFileException](#cfileexception)|Создает объект `CFileException`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileException::ErrnoToException](#errnotoexception)|Возвращает вызвать код, соответствующий номеру ошибки во время выполнения.|  
|[CFileException::GetErrorMessage](#geterrormessage)|Получает сообщение, описывающее исключение.|  
|[CFileException::OsErrorToException](#oserrortoexception)|Возвращает код причины, соответствующий код ошибки операционной системы.|  
|[CFileException::ThrowErrno](#throwerrno)|Исключение файла на основе номера ошибки среды выполнения.|  
|[CFileException::ThrowOsError](#throwoserror)|Исключение файла на основе по номеру ошибки операционной системы.|  
  
### <a name="public-data-members"></a>Открытые члены данных  
  
|Имя|Описание:|  
|----------|-----------------|  
|[CFileException::m_cause](#m_cause)|Содержит переносимого кода, соответствующий причину исключения.|  
|[CFileException::m_lOsError](#m_loserror)|Содержит номер ошибки связанные операционной системы.|  
|[CFileException::m_strFileName](#m_strfilename)|Содержит имя файла для этого исключения.|  
  
## <a name="remarks"></a>Примечания  
 `CFileException` Класс содержит открытые члены данных, содержащих причина переносимого кода и номер ошибки операционной системы зависящие от. Этот класс также предоставляет статических функций-членов для исключения файлов и возвращающие коды причины ошибки операционной системы и ошибки времени выполнения C.  
  
 `CFileException`объекты конструирования и исключение `CFile` функции-члены и функции-члены из производных классов. Эти объекты в области доступны **ПЕРЕХВАТЫВАТЬ** выражение. Для обеспечения переносимости следует используйте только тот код причины для получения причину исключения. Дополнительные сведения об исключениях см. в статье [обработки исключений (MFC)](../../mfc/exception-handling-in-mfc.md).  
  
## <a name="inheritance-hierarchy"></a>Иерархия наследования  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CException](../../mfc/reference/cexception-class.md)  
  
 `CFileException`  
  
## <a name="requirements"></a>Требования  
 **Заголовок:** afx.h  
  
##  <a name="cfileexception"></a>CFileException::CFileException  
 Создает `CFileException` объект, который хранит код причину и код операционной системы в объекте.  
  
```  
CFileException(
    int cause = CFileException::none,  
    LONG lOsError = -1,  
    LPCTSTR lpszArchiveName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `cause`  
 Переменной перечисляемого типа, указывающее причину создания исключения. В разделе [CFileException::m_cause](#m_cause) список возможных значений.  
  
 `lOsError`  
 Операционной системе конкретного причину исключения, если он доступен. `lOsError` Параметр предоставляет больше сведений, чем `cause` does.  
  
 `lpszArchiveName`  
 Указывает строку, содержащую имя `CFile` объекта, вызвавшего исключение.  
  
### <a name="remarks"></a>Примечания  
 Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowFileException](exception-processing.md#afxthrowfileexception).  
  
> [!NOTE]
>  Переменная `lOsError` применяется только к `CFile` и `CStdioFile` объектов. `CMemFile` Класса не может обрабатывать этот код ошибки.  
  
##  <a name="errnotoexception"></a>CFileException::ErrnoToException  
 Преобразует значение заданного библиотеки времени выполнения ошибки `CFileException` ошибки значения перечисления.  
  
```  
static int PASCAL ErrnoToException(int nErrno);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrno`  
 Целочисленный код ошибки, определенный в файл во время выполнения включения ERRNO. З.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления, которое соответствует значению ошибки данной библиотеки времени выполнения.  
  
### <a name="remarks"></a>Примечания  
 В разделе [CFileException::m_cause](#m_cause) список возможных значений перечисления.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]  
  
##  <a name="geterrormessage"></a>CFileException::GetErrorMessage  
 Извлекает текст с описанием исключения.  
  
```  
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,  
    UINT nMaxError,  
    PUINT pnHelpContext = NULL) const;  
```  
  
### <a name="parameters"></a>Параметры  
 [in, out] `lpszError`  
 Указатель на буфер, получающий сообщение об ошибке.  
  
 [in] `nMaxError`  
 Максимальное число символов, которые может вместить указанного буфера. Это включает завершающий нуль-символ.  
  
 [in, out] `pnHelpContext`  
 Указатель на целое число без знака, который получает идентификатор контекста справки. Если `NULL`, идентификатор не возвращается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `TRUE`Если метод выполнен успешно; в противном случае `FALSE`.  
  
### <a name="remarks"></a>Примечания  
 Если указанный буфер слишком мал, сообщение отбрасывается.  
  
### <a name="example"></a>Пример  
 В следующем примере используется `CFileException::GetErrorMessage`.  
  
 [!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]  
  
##  <a name="m_cause"></a>CFileException::m_cause  
 Содержит значения, заданные перечисляемым типом `CFileException`.  
  
```  
int m_cause;  
```  
  
### <a name="remarks"></a>Примечания  
 Этот член данных — это открытая переменная типа `int`. Перечислители и их значение представлено далее.  
  
- `CFileException::none`0: не возникло ошибок.  
  
- `CFileException::genericException`1: произошла неизвестная ошибка.  
  
- `CFileException::fileNotFound`2: не удалось найти файл.  
  
- `CFileException::badPath`3: все или часть пути являются недопустимыми.  
  
- `CFileException::tooManyOpenFiles`4: превышено разрешенное число открытых файлов.  
  
- `CFileException::accessDenied`5: файл будет недоступен.  
  
- `CFileException::invalidFile`6: попытка использовать недопустимый дескриптор файла.  
  
- `CFileException::removeCurrentDir`7: невозможно удалить текущий рабочий каталог.  
  
- `CFileException::directoryFull`8: нет записей каталога больше нет.  
  
- `CFileException::badSeek`9: произошла ошибка при попытке задания указателя файла.  
  
- `CFileException::hardIO`10: произошла аппаратная ошибка.  
  
- `CFileException::sharingViolation`11: ОБЩИЙ РЕСУРС. Exe-ФАЙЛ не был загружен, или блокирована область общего доступа.  
  
- `CFileException::lockViolation`12: попытка блокировки уже заблокированной области.  
  
- `CFileException::diskFull`14: диск заполнен.  
  
- `CFileException::endOfFile`15: достигнут конец файла.  
  
    > [!NOTE]
    >  Перечислители причины `CFileException` отличаются от перечислителей причины `CArchiveException`.  
  
    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Взамен рекомендуется использовать `genericException`. Если `generic` используется в приложении и создан с помощью /clr, итоговые синтаксические ошибки будет сложно интерпретировать.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]  
  
##  <a name="m_loserror"></a>CFileException::m_lOsError  
 Содержит код ошибки операционной системы для этого исключения.  
  
```  
LONG m_lOsError;  
```  
  
### <a name="remarks"></a>Примечания  
 В разделе технической документации операционной системы для получения списка кодов ошибок. Этот член данных — это открытая переменная типа **ДЛИННЫЕ**.  
  
##  <a name="m_strfilename"></a>CFileException::m_strFileName  
 Содержит имя файла для данного условия исключения.  
  
```  
CString m_strFileName;  
```  
  
##  <a name="oserrortoexception"></a>CFileException::OsErrorToException  
 Возвращает перечислитель, который соответствует данной `lOsError` значение. Если код ошибки неизвестен, то функция возвращает **CFileException::generic**.  
  
```  
static int PASCAL OsErrorToException(LONG lOsError);
```  
  
### <a name="parameters"></a>Параметры  
 `lOsError`  
 Код ошибки операционной системы уровне.  
  
### <a name="return-value"></a>Возвращаемое значение  
 Значение перечисления, которое соответствует значению данной ошибки операционной системы.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]  
  
##  <a name="throwerrno"></a>CFileException::ThrowErrno  
 Создает `CFileException` объект, соответствующий данной `nErrno` значение, то создается исключение.  
  
```  
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `nErrno`  
 Целочисленный код ошибки, определенный в файл во время выполнения включения ERRNO. З.  
  
 `lpszFileName`  
 Указатель на строку, содержащую имя файла, который вызвал исключение, если он доступен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]  
  
##  <a name="throwoserror"></a>CFileException::ThrowOsError  
 Создает `CFileException` в зависимости от заданного `lOsError` значение. Если код ошибки неизвестен, то функция создает исключение, закодировано как **CFileException::generic**.  
  
```  
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```  
  
### <a name="parameters"></a>Параметры  
 `lOsError`  
 Код ошибки операционной системы уровне.  
  
 `lpszFileName`  
 Указатель на строку, содержащую имя файла, который вызвал исключение, если он доступен.  
  
### <a name="example"></a>Пример  
 [!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]  
  
## <a name="see-also"></a>См. также  
 [CException-класс](../../mfc/reference/cexception-class.md)   
 [Диаграмма иерархии](../../mfc/hierarchy-chart.md)   
 [Обработка исключений](../../mfc/reference/exception-processing.md)



