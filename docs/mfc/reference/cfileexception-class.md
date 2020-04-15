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
ms.openlocfilehash: 2d1025ca33d5641982ba52f1ac539db85df3bfd5
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373896"
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
|[CFileИсключение::CFileException](#cfileexception)|Формирует объект `CFileException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CFileException::ErrnoToException](#errnotoexception)|Возвраты вызывают код, соответствующий номеру ошибки времени выполнения.|
|[CFileException::GetErrorMessage](#geterrormessage)|Извлекает сообщение, описывающее исключение.|
|[CFileException::Ошибкатоисключение](#oserrortoexception)|Возвращает код причины, соответствующий коду ошибки операционной системы.|
|[CFileException::ThrowErrno](#throwerrno)|Выбрасывает исключение файла на основе номера ошибки времени выполнения.|
|[CFileException::ThrowosОшибка](#throwoserror)|Выбрасывает исключение файла на основе номера ошибки операционной системы.|

### <a name="public-data-members"></a>Открытые члены данных

|Имя|Описание|
|----------|-----------------|
|[CFileException::m_cause](#m_cause)|Содержит портативный код, соответствующий причине исключения.|
|[CFileException::m_lOsError](#m_loserror)|Содержит связанный номер ошибки операционной системы.|
|[CFileException::m_strFileName](#m_strfilename)|Содержит имя файла для этого исключения.|

## <a name="remarks"></a>Remarks

Класс `CFileException` включает в себя открытых членов данных, которые держат портативный код причины и номер ошибки, специфичный для операционной системы. Класс также предоставляет функции статических членов для метания исключений файлов и для возврата кодов причин как для ошибок операционной системы, так и для ошибок времени выполнения C.

`CFileException`объекты строятся и `CFile` выбрасываются в функции членов и в функции членов производных классов. Эти объекты можно получить в рамках выражения **CATCH.** Для переносимости используйте только код причины, чтобы получить причину исключения. Для получения дополнительной информации об [Exception Handling (MFC)](../../mfc/exception-handling-in-mfc.md)исключениях см.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cfileexceptioncfileexception"></a><a name="cfileexception"></a>CFileИсключение::CFileException

Строит `CFileException` объект, который хранит код причины и код операционной системы в объекте.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*cause*<br/>
Перечисленная переменная типа, указывающепричина причину исключения. Смотрите [CFileException::m_cause](#m_cause) для списка возможных значений.

*lOsОшибка*<br/>
По конкретной причине исключения, если это возможно, является причиной, конкретной для операционной системы. Параметр *lOsError* предоставляет больше информации, чем *причина.*

*lpszArchiveName*<br/>
Указывает на строку, содержащую имя `CFile` объекта, вызывающего исключение.

### <a name="remarks"></a>Remarks

Не используйте этот конструктор напрямую, а скорее позвоните в глобальную функцию [AfxThrowFileException](exception-processing.md#afxthrowfileexception).

> [!NOTE]
> Переменная *lOsError* применяется `CFile` `CStdioFile` только к объектам и объектам. Класс `CMemFile` не обрабатывает этот код ошибки.

## <a name="cfileexceptionerrnotoexception"></a><a name="errnotoexception"></a>CFileException::ErrnoToException

Преобразует заданное значение ошибки в `CFileException` библиотеке времени выполнения в перечисленное значение ошибки.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Параметры

*nЭрно*<br/>
Целый код ошибки, определенный в времени выполнения, включает файл ERRNO. H.

### <a name="return-value"></a>Возвращаемое значение

Перечисленное значение, которое соответствует заданной стоимости ошибки в библиотеке завремя.

### <a name="remarks"></a>Remarks

Смотрите [CFileException::m_cause](#m_cause) для списка возможных перечисленных значений.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

## <a name="cfileexceptiongeterrormessage"></a><a name="geterrormessage"></a>CFileException::GetErrorMessage

Извлекает текст, описывающий исключение.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Параметры

*lpszОшибка*<br/>
(в, вне) Указатель на буфер, который получает сообщение об ошибке.

*nMaxОшибка*<br/>
(в) Максимальное количество символов, которые может удерживать указанный буфер. Это включает в себя прекращение нулевой характер.

*pnHelpКонтекст*<br/>
(в, вне) Указатель на неподписанный идентификатор контекста. Если `NULL`ID не возвращается.

### <a name="return-value"></a>Возвращаемое значение

ПРАВДА, если метод был успешным; в противном случае FALSE.

### <a name="remarks"></a>Remarks

Если указанный буфер слишком мал, сообщение об ошибке усечено.

### <a name="example"></a>Пример

В следующем примере используется функция `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

## <a name="cfileexceptionm_cause"></a><a name="m_cause"></a>CFileException::m_cause

Содержит значения, заданные перечисляемым типом `CFileException`.

```
int m_cause;
```

### <a name="remarks"></a>Remarks

Этот член данных является общедоступной переменной типа **Int.** Регистраторы и их значения таковы:

- `CFileException::none`0: Ошибки не произошло.

- `CFileException::genericException`1: Произошла неопределенная ошибка.

- `CFileException::fileNotFound`2: Файл не может быть обнаружен.

- `CFileException::badPath`3: Все или часть пути недействительна.

- `CFileException::tooManyOpenFiles`4: Было превышено допустимое количество открытых файлов.

- `CFileException::accessDenied`5: Доступ к файлу не удалось.

- `CFileException::invalidFile`6: Была предпринята попытка использовать недействительную ручку файла.

- `CFileException::removeCurrentDir`7: Текущий рабочий каталог не может быть удален.

- `CFileException::directoryFull`8: Есть не более каталогзаписей.

- `CFileException::badSeek`9: Была ошибка, пытаясь установить указатель файла.

- `CFileException::hardIO`10: Произошла аппаратная ошибка.

- `CFileException::sharingViolation`11: ДОЛЯ. EXE не был загружен, или общий регион был заблокирован.

- `CFileException::lockViolation`12: Была попытка заблокировать область, которая уже была заблокирована.

- `CFileException::diskFull`14: Диск полон.

- `CFileException::endOfFile`15: Конец файла был достигнут.

    > [!NOTE]
    >  Перечислители причины `CFileException` отличаются от перечислителей причины `CArchiveException`.

    > [!NOTE]
    > `CArchiveException::generic` не рекомендуется к использованию. Используйте вместо этого `genericException`. Если **общий используется** в приложении и построен с /clr, возникающие ошибки синтаксиса не легко расшифровать.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

## <a name="cfileexceptionm_loserror"></a><a name="m_loserror"></a>CFileException::m_lOsError

Содержит код ошибки операционной системы для этого исключения.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Remarks

Ознакомьтесь с техническим руководством операционной системы для перечисления кодов ошибок. Этот член данных является общедоступной переменной типа LONG.

## <a name="cfileexceptionm_strfilename"></a><a name="m_strfilename"></a>CFileException::m_strFileName

Содержит имя файла для этого состояния исключения.

```
CString m_strFileName;
```

## <a name="cfileexceptionoserrortoexception"></a><a name="oserrortoexception"></a>CFileException::Ошибкатоисключение

Возвращает регистратор, соответствующий заданной стоимости *lOsError.* Если код ошибки неизвестен, `CFileException::generic`функция возвращается.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Параметры

*lOsОшибка*<br/>
Код ошибки, связанные с операционной системой.

### <a name="return-value"></a>Возвращаемое значение

Перечисленное значение, которое соответствует заданной стоимости ошибки операционной системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

## <a name="cfileexceptionthrowerrno"></a><a name="throwerrno"></a>CFileException::ThrowErrno

Строит объект, `CFileException` соответствующий заданной стоимости *nErrno,* а затем бросает исключение.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*nЭрно*<br/>
Целый код ошибки, определенный в времени выполнения, включает файл ERRNO. H.

*lpszFileName*<br/>
Указатель строки, содержащей имя файла, вызвавшего исключение, если он доступен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

## <a name="cfileexceptionthrowoserror"></a><a name="throwoserror"></a>CFileException::ThrowosОшибка

Бросает соответствующее `CFileException` заданное значение *lOsError.* Если код ошибки неизвестен, функция бросает исключение, `CFileException::generic`закодированное как.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*lOsОшибка*<br/>
Код ошибки, связанные с операционной системой.

*lpszFileName*<br/>
Указатель строки, содержащей имя файла, вызвавшего исключение, если он доступен.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)
