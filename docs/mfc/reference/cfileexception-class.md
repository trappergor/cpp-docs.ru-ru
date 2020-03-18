---
title: Класс Кфиликсцептион
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
ms.openlocfilehash: a3514c76d4136fe2bc0b096cc382e6f7f4dd3392
ms.sourcegitcommit: 7ecd91d8ce18088a956917cdaf3a3565bd128510
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 03/16/2020
ms.locfileid: "79424419"
---
# <a name="cfileexception-class"></a>Класс Кфиликсцептион

Представляет состояние, связанное с файлом исключения.

## <a name="syntax"></a>Синтаксис

```
class CFileException : public CException
```

## <a name="members"></a>Члены

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Description|
|----------|-----------------|
|[Кфиликсцептион:: Кфиликсцептион](#cfileexception)|Формирует объект `CFileException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Description|
|----------|-----------------|
|[Кфиликсцептион:: Еррнотоексцептион](#errnotoexception)|Возвращает код, соответствующий номеру ошибки времени выполнения.|
|[Кфиликсцептион:: Жетеррормессаже](#geterrormessage)|Получает сообщение, описывающее исключение.|
|[Кфиликсцептион:: Осеррортоексцептион](#oserrortoexception)|Возвращает код причины, соответствующий коду ошибки операционной системы.|
|[Кфиликсцептион:: Сроверрно](#throwerrno)|Создает исключение файла на основе номера ошибки времени выполнения.|
|[Кфиликсцептион:: Сровосеррор](#throwoserror)|Создает исключение файла на основе номера ошибки операционной системы.|

### <a name="public-data-members"></a>Открытые элементы данных

|Имя|Description|
|----------|-----------------|
|[Кфиликсцептион:: m_cause](#m_cause)|Содержит переносимый код, соответствующий причине исключения.|
|[Кфиликсцептион:: m_lOsError](#m_loserror)|Содержит номер связанной ошибки операционной системы.|
|[Кфиликсцептион:: m_strFileName](#m_strfilename)|Содержит имя файла для этого исключения.|

## <a name="remarks"></a>Remarks

Класс `CFileException` содержит открытые члены данных, которые содержат переносимый код причины и номер ошибки, зависящий от операционной системы. Класс также предоставляет статические функции-члены для генерации исключений файлов и для возврата кодов причин ошибок операционной системы и ошибок времени выполнения C.

`CFileException` объекты создаются и создаются в `CFile` функциях элементов и в функциях членов производных классов. Доступ к этим объектам можно получить в области выражения **catch** . Для обеспечения переносимости используйте только код причины, чтобы получить причину исключения. Дополнительные сведения об исключениях см. в статье [обработка исключений (MFC)](../../mfc/exception-handling-in-mfc.md).

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](../../mfc/reference/cobject-class.md)

[CException](../../mfc/reference/cexception-class.md)

`CFileException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cfileexception"></a>Кфиликсцептион:: Кфиликсцептион

Конструирует объект `CFileException`, в котором хранится код причины и код операционной системы в объекте.

```
CFileException(
    int cause = CFileException::none,
    LONG lOsError = -1,
    LPCTSTR lpszArchiveName = NULL);
```

### <a name="parameters"></a>Параметры

*cause*<br/>
Переменная перечислимого типа, указывающая причину исключения. Список возможных значений см. в разделе [кфиликсцептион:: m_cause](#m_cause) .

*лосеррор*<br/>
Причина исключения, зависящая от операционной системы, если она доступна. Параметр *лосеррор* предоставляет больше информации, чем *Причина* .

*лпсзарчивенаме*<br/>
Указывает на строку, содержащую имя объекта `CFile`, вызвавшего исключение.

### <a name="remarks"></a>Remarks

Не используйте этот конструктор напрямую, а вызовите глобальную функцию [афкссровфиликсцептион](exception-processing.md#afxthrowfileexception).

> [!NOTE]
>  Переменная *лосеррор* применяется только к `CFile` и `CStdioFile` объектам. Класс `CMemFile` не обрабатывает этот код ошибки.

##  <a name="errnotoexception"></a>Кфиликсцептион:: Еррнотоексцептион

Преобразует заданное значение ошибки библиотеки времени выполнения в `CFileException` перечислимое значение ошибки.

```
static int PASCAL ErrnoToException(int nErrno);
```

### <a name="parameters"></a>Параметры

*неррно*<br/>
Целочисленный код ошибки, как определено в файле времени выполнения. Высоты.

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, соответствующее указанному значению ошибки библиотеки времени выполнения.

### <a name="remarks"></a>Remarks

Список возможных перечислимых значений см. в разделе [кфиликсцептион:: m_cause](#m_cause) .

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#26](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_1.cpp)]

##  <a name="geterrormessage"></a>Кфиликсцептион:: Жетеррормессаже

Извлекает текст, описывающий исключение.

```
virtual BOOL GetErrorMessage(
    LPTSTR lpszError,
    UINT nMaxError,
    PUINT pnHelpContext = NULL) const;
```

### <a name="parameters"></a>Параметры

*лпсзеррор*<br/>
[вход, выход] Указатель на буфер, который получает сообщение об ошибке.

*нмаксеррор*<br/>
окне Максимальное число символов, которое может хранить указанный буфер. Сюда входит завершающий нуль символ.

*пнхелпконтекст*<br/>
[вход, выход] Указатель на целое число без знака, которое получает идентификатор контекста справки. Если `NULL`, идентификатор не возвращается.

### <a name="return-value"></a>Возвращаемое значение

Значение TRUE, если метод выполнен успешно; в противном случае — FALSE.

### <a name="remarks"></a>Remarks

Если указанный буфер слишком мал, сообщение об ошибке усекается.

### <a name="example"></a>Пример

В следующем примере используется функция `CFileException::GetErrorMessage`.

[!code-cpp[NVC_MFCExceptions#22](../../mfc/codesnippet/cpp/cfileexception-class_2.cpp)]

##  <a name="m_cause"></a>Кфиликсцептион:: m_cause

Содержит значения, заданные перечисляемым типом `CFileException`.

```
int m_cause;
```

### <a name="remarks"></a>Remarks

Этот элемент данных является открытой переменной типа **int**. Ниже перечислены перечислители и их значения.

- `CFileException::none` 0: не произошла ошибка.

- `CFileException::genericException` 1: Произошла неопределенная ошибка.

- `CFileException::fileNotFound` 2: файл не найден.

- `CFileException::badPath` 3: недопустимый полный или часть пути.

- `CFileException::tooManyOpenFiles` 4: превышено допустимое число открытых файлов.

- `CFileException::accessDenied` 5: файл недоступен.

- `CFileException::invalidFile` 6: предпринята попытка использовать Недопустимый файловый обработчик.

- `CFileException::removeCurrentDir` 7: невозможно удалить текущий рабочий каталог.

- `CFileException::directoryFull` 8: больше нет записей каталога.

- `CFileException::badSeek` 9: произошла ошибка при попытке установить указатель на файл.

- `CFileException::hardIO` 10: произошла аппаратная ошибка.

- `CFileException::sharingViolation` 11: общий доступ. EXE-файл не был загружен, или общий регион заблокирован.

- `CFileException::lockViolation` 12: предпринята попытка заблокировать уже заблокированный регион.

- `CFileException::diskFull` 14: диск заполнен.

- `CFileException::endOfFile` 15: достигнут конец файла.

    > [!NOTE]
    >  Перечислители причины `CFileException` отличаются от перечислителей причины `CArchiveException`.

    > [!NOTE]
    > Параметр `CArchiveException::generic` использовать не рекомендуется. Используйте вместо этого `genericException`. Если **универсальное** приложение используется в приложении и строится с помощью параметра/CLR, то в результате синтаксических ошибок не будет легко расшифроваться.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#30](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_3.cpp)]

##  <a name="m_loserror"></a>Кфиликсцептион:: m_lOsError

Содержит код ошибки операционной системы для этого исключения.

```
LONG m_lOsError;
```

### <a name="remarks"></a>Remarks

Список кодов ошибок см. в техническом руководстве по операционной системе. Этот элемент данных является открытой переменной типа LONG.

##  <a name="m_strfilename"></a>Кфиликсцептион:: m_strFileName

Содержит имя файла для этого условия исключения.

```
CString m_strFileName;
```

##  <a name="oserrortoexception"></a>Кфиликсцептион:: Осеррортоексцептион

Возвращает перечислитель, соответствующий заданному значению *лосеррор* . Если код ошибки неизвестен, функция возвращает `CFileException::generic`.

```
static int PASCAL OsErrorToException(LONG lOsError);
```

### <a name="parameters"></a>Параметры

*лосеррор*<br/>
Код ошибки, относящийся к операционной системе.

### <a name="return-value"></a>Возвращаемое значение

Перечислимое значение, соответствующее заданному значению ошибки операционной системы.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#27](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_4.cpp)]

##  <a name="throwerrno"></a>Кфиликсцептион:: Сроверрно

Создает объект `CFileException`, соответствующий заданному значению *неррно* , а затем создает исключение.

```
static void PASCAL ThrowErrno(int nErrno, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*неррно*<br/>
Целочисленный код ошибки, как определено в файле времени выполнения. Высоты.

*лпсзфиленаме*<br/>
Указатель на строку, содержащую имя файла, вызвавшего исключение, если он есть.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#28](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_5.cpp)]

##  <a name="throwoserror"></a>Кфиликсцептион:: Сровосеррор

Создает `CFileException`, соответствующий заданному значению *лосеррор* . Если код ошибки неизвестен, функция создает исключение, закодированное как `CFileException::generic`.

```
static void PASCAL ThrowOsError(LONG lOsError, LPCTSTR lpszFileName = NULL);
```

### <a name="parameters"></a>Параметры

*лосеррор*<br/>
Код ошибки, относящийся к операционной системе.

*лпсзфиленаме*<br/>
Указатель на строку, содержащую имя файла, вызвавшего исключение, если он есть.

### <a name="example"></a>Пример

[!code-cpp[NVC_MFCFiles#29](../../atl-mfc-shared/reference/codesnippet/cpp/cfileexception-class_6.cpp)]

## <a name="see-also"></a>См. также раздел

[Класс CException](../../mfc/reference/cexception-class.md)<br/>
[Диаграмма иерархии](../../mfc/hierarchy-chart.md)<br/>
[Обработка исключений](../../mfc/reference/exception-processing.md)
