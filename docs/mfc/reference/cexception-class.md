---
title: Класс CException
ms.date: 11/04/2016
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
ms.openlocfilehash: 689afa2ffbc27feec6f9e1704a6b295d5eabfaee
ms.sourcegitcommit: 0ab61bc3d2b6cfbd52a16c6ab2b97a8ea1864f12
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/23/2019
ms.locfileid: "62164004"
---
# <a name="cexception-class"></a>Класс CException

Базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|name|Описание|
|----------|-----------------|
|[CException::CException](#cexception)|Создает объект `CException`.|

### <a name="public-methods"></a>Открытые методы

|name|Описание|
|----------|-----------------|
|[CException::Delete](#delete)|Удаляет `CException` объекта.|
|[CException::ReportError](#reporterror)|Отправит сообщение об ошибке в окне сообщения для пользователя.|

## <a name="remarks"></a>Примечания

Так как `CException` — это абстрактный базовый класс, нельзя создать `CException` объектов непосредственно, необходимо создать объекты из производных классов. Если вам нужно создать свой собственный `CException`-класс стиля, используйте один из производных классов, перечисленных выше, как модель. Убедитесь, что производный класс также используется `IMPLEMENT_DYNAMIC`.

Ниже перечислены производные классы и их описания.

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для исключений MFC, критическими ресурсами|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Условие исключения недопустимого аргумента|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение Out of memory|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос неподдерживаемая операция|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключения для конкретных архива|
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение файлов|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows, не найден или не создаваемый объект|
|[COleException](../../mfc/reference/coleexception-class.md)|Исключения OLE|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключение базы данных (то есть условия возникновения исключений возникающие для классов баз данных MFC, в зависимости от Open Database Connectivity)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Исключения OLE диспетчеризации (автоматизация)|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает, что ресурс не найден|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Исключение объекта доступа к данным (то есть условия возникновения исключений возникающие для классов DAO)|
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Исключение Интернет (то есть условия возникновения исключений возникающие для классов в Интернете).|

Эти исключения предназначены для использования с [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [попробуйте](exception-processing.md#try), [catch](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), и [end_catch](exception-processing.md#end_catch) макросы. Дополнительные сведения об исключениях см. в разделе [обработка исключений](exception-processing.md), или см. в статье [обработка исключений (MFC)](../exception-handling-in-mfc.md).

Для перехвата определенного исключения, используйте соответствующий производный класс. Чтобы перехватить все типы исключений, используйте `CException`, а затем с помощью [CObject::IsKindOf](cobject-class.md#iskindof) для различения `CException`-производные классы. Обратите внимание, что `CObject::IsKindOf` работает только для классов, объявленных с [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) макрос, чтобы воспользоваться преимуществами динамической проверки типов. Любой `CException`-производного класса, который создается следует использовать `IMPLEMENT_DYNAMIC` макрос, слишком.

Вы можете сообщить сведения об исключениях для пользователя, вызвав [GetErrorMessage](cfileexception-class.md#geterrormessage) или [ReportError](#reporterror), две функции-члены, которые работают с любой из `CException`производных классах.

Если исключение перехватывается в один из макросов, `CException` объект автоматически удаляется; не удаляйте его самостоятельно. Если исключение будет перехвачено с помощью **catch** ключевое слово, она не удаляется автоматически. См. в статье [обработка исключений (MFC)](../exception-handling-in-mfc.md) Дополнительные сведения о том, когда для удаления объекта об исключении.

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

##  <a name="cexception"></a>  CException::CException

Эта функция-член создает `CException` объекта.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*b_AutoDelete*<br/>
Укажите значение TRUE, если память для `CException` объект выделен в куче. Это приведет к `CException` объект будет удален при `Delete` функция-член вызывается для удаления исключение. Укажите значение FALSE, если `CException` объект находится в стеке или — это глобальный объект. В этом случае `CException` объект не будет удалено, когда `Delete` вызывается функция-член.

### <a name="remarks"></a>Примечания

Обычно никогда не потребовалось бы вызвать этот конструктор напрямую. Функция, которая создает исключение следует создать экземпляр `CException`-производного класса и вызвать его конструктор, или его необходимо использовать один из MFC вызвать исключение функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), могут породить предопределенного типа. Эта документация предоставляется только для полноты информации.

##  <a name="delete"></a>  CException::Delete

Эта функция проверяет `CException` объект был создан в куче, и если да, он вызывает **удалить** оператор в объекте.

```
void Delete();
```

### <a name="remarks"></a>Примечания

При удалении `CException` , используйте `Delete` функция-член для удаления исключение. Не используйте **удалить** оператор напрямую, так как `CException` объект может быть глобальный объект, или будут созданы в стеке.

Можно указать, должен ли объект быть удален при создании объекта. Дополнительные сведения см. в разделе [CException::CException](#cexception).

Необходимо вызвать `Delete` при использовании C++ **попробуйте**- **catch** механизм. При использовании макросов MFC **попробуйте** и **CATCH**, а затем эти макросы автоматически вызывает эту функцию.

### <a name="example"></a>Пример

```cpp
CFile* pFile = NULL;
// Constructing a CFile object with this override may throw
// a CFile exception, and won't throw any other exceptions.
// Calling CString::Format() may throw a CMemoryException,
// so we have a catch block for such exceptions, too. Any
// other exception types this function throws will be
// routed to the calling function.
// Note that this example performs the same actions as the
// example for CATCH, but uses C++ try/catch syntax instead
// of using the MFC TRY/CATCH macros. This sample must use
// CException::Delete() to delete the exception objects
// before closing the catch block, while the CATCH example
// implicitly performs the deletion via the macros.
try
{
   pFile = new CFile(_T("C:\\WINDOWS\\SYSTEM.INI"),
      CFile::modeRead | CFile::shareDenyNone);
   ULONGLONG ullLength = pFile->GetLength();
   CString str;
   str.Format(_T("Your SYSTEM.INI file is %u bytes long."), ullLength);
   AfxMessageBox(str);
}
catch(CFileException* pEx)
{
   // Simply show an error message to the user.
   pEx->ReportError();
   pEx->Delete();
}
catch(CMemoryException* pEx)
{
   // We can't recover from this memory exception, so we'll
   // just terminate the app without any cleanup. Normally, an
   // an application should do everything it possibly can to
   // clean up properly and _not_ call AfxAbort().
   pEx->Delete();
   AfxAbort();
}
// If an exception occurrs in the CFile constructor,
// the language will free the memory allocated by new
// and will not complete the assignment to pFile.
// Thus, our clean-up code needs to test for NULL.
if (pFile != NULL)
{
   pFile->Close();
   delete pFile;
}
```

##  <a name="reporterror"></a>  CException::ReportError

Вызывайте эту функцию члена для отчета текст ошибки в окне сообщения для пользователя.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Задает стиль окна сообщения. Применить любое сочетание [стили окна сообщений](styles-used-by-mfc.md#message-box-styles) в поле. Если этот параметр не задан, по умолчанию используется MB_OK.

*nMessageID*<br/>
Указывает идентификатор ресурса (элемент строку таблицы) сообщение, отображаемое, если объект исключения не содержит сообщение об ошибке. Если значение равно 0, сообщение «сообщение об ошибке не is available» отображается.

### <a name="return-value"></a>Возвращаемое значение

`AfxMessageBox` Значение; в противном случае — значение 0, если не хватает памяти, чтобы отобразить окно сообщения. См. в разделе [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) возможные возвращаемые значения.

### <a name="example"></a>Пример

Ниже приведен пример использования `CException::ReportError`. Другой пример, см. в примере [CATCH](exception-processing.md#catch).

```cpp
CFile fileInput;
CFileException ex;

// try to open a file for reading.
// The file will certainly not
// exist because there are too many explicit
// directories in the name.

// if the call to Open() fails, ex will be
// initialized with exception
// information.  the call to ex.ReportError() will
// display an appropriate
// error message to the user, such as
// "\Too\Many\Bad\Dirs.DAT contains an
// invalid path."  The error message text will be
// appropriate for the
// file name and error condition.

if (!fileInput.Open(_T("\\Too\\Many\\Bad\\Dirs.DAT"), CFile::modeRead, &ex))
{
  ex.ReportError();
}
else
{
  // the file was opened, so do whatever work
  // with fileInput we were planning...

  fileInput.Close();
}
```

## <a name="see-also"></a>См. также

[Класс CObject](cobject-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)<br/>
[Обработка исключений](exception-processing.md)<br/>
[Инструкции: Создать собственные пользовательские классы исключений](http://go.microsoft.com/fwlink/p/?linkid=128045)
