---
title: Класс CFileException
ms.date: 11/04/2016
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
ms.openlocfilehash: e6b1b25f9125701a212f379c925a80ff888d58f3
ms.sourcegitcommit: 6052185696adca270bc9bdbec45a626dd89cdcdd
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 10/31/2018
ms.locfileid: "50485828"
---
# <a name="cfileexception-class"></a>Класс CFileException

Представляет состояние, связанное с файлом исключения.

## <a name="syntax"></a>Синтаксис

```
class CFileException : public CException
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CFileException::CFileException](#cfileexception)|Создает объект `CFileException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|Возвращает вызвать код, соответствующий номеру ошибки времени выполнения.|
|[CFileException::GetErrorMessage](#geterrormessage)|Получает сообщение, описывающее исключение.|
|[CFileException::OsErrorToException](#oserrortoexception)|Возвращает причину код, соответствующий код ошибки операционной системы.|
|[CFileException::ThrowErrno](#throwerrno)|Исключение файла по номеру ошибки среды выполнения.|
|[CFileException::ThrowOsError](#throwoserror)|Исключение файла на основе номера ошибки операционной системы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|Содержит переносимого кода, соответствующий причине исключения.|
|[CFileException::m_lOsError](#m_loserror)|Содержит число ошибок, связанных с операционной системы.|
|[CFileException::m_strFileName](#m_strfilename)|Содержит имя файла для этого исключения.|

## <a name="remarks"></a>Примечания

`CFileException` Класс содержит открытые члены данных, которые содержат код переносимой причина и номер ошибки операционной системы — конкретных. Класс также предоставляет статические функции-члены для исключения файлов и возвращающие коды причины ошибки операционной системы и ошибки времени выполнения C.

`CFileException` объекты конструирования и исключение `CFile` функции-члены и функции-члены из производных классов. Эти объекты в пределах доступны **CATCH** выражение. Для переносимости используйте только код причины, чтобы получить причину исключения. Дополнительные сведения об исключениях см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cfileexception"></a>  CFileException::CFileException

Создает `CFileException` объект, который хранит код причину и код операционной системы в объекте.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*Причина*<br/>
Переменной перечисляемого типа, указывающее причину возникновения исключения. См. в разделе [CFileException::m_cause](#m_cause) список возможных значений.

*lOsError*<br/>
Операционной системе конкретного причину возникновения исключения, если он доступен. *LOsError* параметр предоставляет больше информации, чем *вызвать* does.

*lpszArchiveName*<br/>
Указывает на строку, содержащую имя `CFile` объекта, вызвавшего исключение.

### <a name="remarks"></a>Примечания

Не используйте этот конструктор напрямую, но вместо этого вызовите глобальную функцию [AfxThrowFileException](exception-processing.md#afxthrowfileexception).

> [!NOTE]
>  Переменная *lOsError* применяется только к `CFile` и `CStdioFile` объектов. `CMemFile` Класс не обрабатывает этот код ошибки.

##  <a name="errnotoexception"></a>  CFileException::ErrnoToException

Преобразует значение заданного библиотеки времени выполнения ошибка `CFileException` перечисленное значение ошибки.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Параметры

*nErrno*<br/>
Целочисленный код ошибки как определено во время выполнения включаемом файле ERRNO. З.

### <a name="return-value"></a>Возвращаемое значение

Значение перечисления, которое соответствует значению ошибки данной библиотеки времени выполнения.

### <a name="remarks"></a>Примечания

См. в разделе [CFileException::m_cause](#m_cause) список возможных значений перечисления.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>  CFileException::GetErrorMessage

Извлекает текст с описанием исключения.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszError*<br/>
[in, out] Указатель на буфер, получающий сообщение об ошибке.

*nMaxError*<br/>
[in] Максимальное количество символов, которое может содержать указанного буфера. Это включает завершающий нуль-символ.

*pnHelpContext*<br/>
[in, out] Указатель на целое число без знака, получающий идентификатор контекста справки. Если `NULL`, возвращается идентификатор отсутствует.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод был выполнен успешно; в противном случае — значение FALSE.

### <a name="remarks"></a>Примечания

Если указанный буфер слишком мал, сообщение об ошибке будет усечен.

### <a name="example"></a>Пример

В следующем примере используется `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>  CFileException::m_cause

Содержит значения, заданные перечисляемым типом `CFileException`.

```
int m_cause;
```

### <a name="remarks"></a>Примечания

Этот элемент данных — это открытая переменная типа **int**. Перечислители и их значение представлено далее.

- `CFileException::none` 0: без ошибок.

- `CFileException::genericException` 1: произошла неизвестная ошибка.

- `CFileException::fileNotFound` 2: не удалось найти файл.

- `CFileException::badPath` 3: все или часть пути является недопустимым.

- `CFileException::tooManyOpenFiles` 4: превышено разрешенное число открытых файлов.

- `CFileException::accessDenied` 5: не быть доступа к файлу.

- `CFileException::invalidFile` 6: Произошла попытка использовать недопустимый дескриптор файла.

- `CFileException::removeCurrentDir` 7: невозможно удалить текущий рабочий каталог.

- `CFileException::directoryFull` 8: нет записей каталога больше нет.

- `CFileException::badSeek` 9: произошла ошибка при попытке задания указателя файла.

- `CFileException::hardIO` 10: произошла аппаратная ошибка.

- `CFileException::sharingViolation` 11: ОБЩИЙ РЕСУРС. Exe-ФАЙЛ не был загружен или общий регион заблокирован.

- `CFileException::lockViolation` 12: попытка заблокировать регион, который уже заблокирован.

- `CFileException::diskFull` 14: диск заполнен.

- `CFileException::endOfFile` 15: достигнут конец файла.

    > [!NOTE]
    >  Перечислители причины `CFileException` отличаются от перечислителей причины `CArchiveException`.

    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Взамен рекомендуется использовать `genericException`. Если **универсального** приложения и построения с/CLR, итоговые синтаксические ошибки не может быть нелегко расшифровать.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>  CFileException::m_lOsError

Содержит код ошибки операционной системы для этого исключения.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Примечания

См. в разделе технической документации операционной системы список кодов ошибок. Этот член данных — это открытая переменная типа LONG.

##  <a name="m_strfilename"></a>  CFileException::m_strFileName

Содержит имя файла для данного условия исключения.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>  CFileException::OsErrorToException

Возвращает перечислитель, соответствующий заданной *lOsError* значение. Если код ошибки неизвестен, то функция возвращает `CFileException::generic`.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Параметры

*lOsError*<br/>
Код ошибки операционной системы уровне.

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, соответствующее значению данной ошибки операционной системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>  CFileException::ThrowErrno

Создает `CFileException` объект, соответствующий заданной *nErrno* значение, а затем создает исключение.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*nErrno*<br/>
Целочисленный код ошибки как определено во время выполнения включаемом файле ERRNO. З.

*lpszFileName*<br/>
Указатель на строку, содержащую имя файла, которая вызвала исключение, если он доступен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>  CFileException::ThrowOsError

Создает `CFileException` соответствующий заданного *lOsError* значение. Если код ошибки неизвестен, то функция создает исключение, закодировано как `CFileException::generic`.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*lOsError*<br/>
Код ошибки операционной системы уровне.

*lpszFileName*<br/>
Указатель на строку, содержащую имя файла, которая вызвала исключение, если он доступен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>См. также

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)

