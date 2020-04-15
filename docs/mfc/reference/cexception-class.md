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
ms.openlocfilehash: c3742db7475e626b18e9c073a0b7417a8034863f
ms.sourcegitcommit: c123cc76bb2b6c5cde6f4c425ece420ac733bf70
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 04/14/2020
ms.locfileid: "81373941"
---
# <a name="cexception-class"></a>Класс CException

Базовый класс для всех исключений библиотеки классов Microsoft Foundation.

## <a name="syntax"></a>Синтаксис

```
class AFX_NOVTABLE CException : public CObject
```

## <a name="members"></a>Участники

### <a name="public-constructors"></a>Открытые конструкторы

|Имя|Описание|
|----------|-----------------|
|[CException::CException](#cexception)|Формирует объект `CException`.|

### <a name="public-methods"></a>Открытые методы

|Имя|Описание|
|----------|-----------------|
|[CException::Delete](#delete)|Удаляет `CException` объект.|
|[CException::ReportОшибка](#reporterror)|Сообщает пользователю сообщение об ошибке в поле сообщения.|

## <a name="remarks"></a>Remarks

Потому что `CException` это абстрактный базовый класс, вы не можете создавать `CException` объекты напрямую; необходимо создавать объекты производных классов. Если вам нужно создать `CException`свой собственный класс стиля, используйте один из полученных классов, перечисленных выше, в качестве модели. Убедитесь, что ваш производный класс также использует. `IMPLEMENT_DYNAMIC`

Полученные классы и их описания перечислены ниже:

|||
|-|-|
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для ресурсо-критических исключений MFC|
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Недействительное условие исключения аргумента|
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение из памяти|
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос на неподдерживаемую операцию|
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключение для архива|
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение для конкретных файлов|
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс Windows не найден или не способен к соотвене|
|[COleException](../../mfc/reference/coleexception-class.md)|Исключение OLE|
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключение базы данных (т.е. условия исключения, возникающие для классов баз данных MFC на основе open Database Connectivity)|
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Исключение OL-диспетчерской (автоматизации)|
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, указываво, что ресурс не может быть найден|
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Исключение объектов доступа к данным (т.е. условия исключения, возникающие для классов DAO)|
|[CInternetConnection](../../mfc/reference/cinternetexception-class.md)|Исключение интернета (т.е. условия исключения, возникающие для классов Интернета).|

Эти исключения предназначены для использования с [THROW](exception-processing.md#throw), [THROW_LAST,](exception-processing.md#throw_last) [попробуйте,](exception-processing.md#try) [поймать,](exception-processing.md#catch) [and_catch,](exception-processing.md#and_catch)и [end_catch](exception-processing.md#end_catch) макросов. Для получения дополнительной информации об исключениях см. [Обработка исключений](exception-processing.md)или [см.](../exception-handling-in-mfc.md)

Чтобы поймать конкретное исключение, используйте соответствующий производный класс. Чтобы поймать все типы `CException`исключений, используйте [CObject::IsKindOf,](cobject-class.md#iskindof) чтобы дифференцировать между `CException`-производными классами. Обратите `CObject::IsKindOf` внимание, что работает только для классов, заявленных с [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) макросом, чтобы воспользоваться динамической проверкой типа. Любой `CException`класс, который вы создаете, должен использовать `IMPLEMENT_DYNAMIC` и макрос.

Вы можете сообщить подробности об исключениях для пользователя, позвонив [getErrorMessage](cfileexception-class.md#geterrormessage) или [ReportError](#reporterror), две функции участника, которые работают с любым из `CException`классов, полученных.

Если исключение поймано одним из макросов, `CException` объект удаляется автоматически; не удаляйте его самостоятельно. Если исключение ловится с помощью ключевого слова **catch,** оно не удаляется автоматически. Дополнительную информацию о том, когда следует удалить объект exeption, смотрите в статье [Обобработки исключений (MFC).](../exception-handling-in-mfc.md)

## <a name="inheritance-hierarchy"></a>Иерархия наследования

[CObject](cobject-class.md)

`CException`

## <a name="requirements"></a>Требования

**Заголовок:** afx.h

## <a name="cexceptioncexception"></a><a name="cexception"></a>CException::CException

Эта функция члена `CException` строит объект.

```
explicit CException(BOOL bAutoDelete);
```

### <a name="parameters"></a>Параметры

*b_AutoDelete*<br/>
Укажите TRUE, если `CException` память для объекта была выделена на куче. Это приведет `CException` к удалению объекта `Delete` при вызове функции участника для удаления исключения. Укажите FALSE, находится ли `CException` объект в стеке или является глобальным объектом. В этом случае `CException` объект не будет удален `Delete` при вызове функции участника.

### <a name="remarks"></a>Remarks

Обычно вам никогда не нужно звонить этому конструктору напрямую. Функция, которая бросает исключение, должна создать `CException`экземпляр класса, полученного из-производного, или вызвать его конструктор, или она должна использовать одну из функций метания MFC, такую как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы бросить предопределенный тип. Эта документация предоставляется только для полноты.

## <a name="cexceptiondelete"></a><a name="delete"></a>CException::Delete

Эта функция проверяет, `CException` был ли объект создан на куче, и если да, то она вызывает оператора **удаления** на объекте.

```
void Delete();
```

### <a name="remarks"></a>Remarks

При удалении `CException` объекта используйте функцию `Delete` члена для удаления исключения. Не используйте оператора **удаления** напрямую, поскольку `CException` объект может быть глобальным объектом или создан в стеке.

Можно указать, следует ли удалять объект при построении объекта. Для получения дополнительной информации [см. CException::CException](#cexception).

Вам `Delete` нужно позвонить только в том случае, если вы используете механизм**ловли ловких ловли** СЗ. **try**-  Если вы используете макросы MFC **TRY** и **CATCH,** то эти макросы автоматически вызовут эту функцию.

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

## <a name="cexceptionreporterror"></a><a name="reporterror"></a>CException::ReportОшибка

Вызовите эту функцию участника, чтобы сообщить пользователю текст ошибки в поле сообщения.

```
virtual int ReportError(
    UINT nType = MB_OK,
    UINT nMessageID = 0);
```

### <a name="parameters"></a>Параметры

*nType*<br/>
Определяет стиль коробки сообщений. Примените любую комбинацию [стилей почтового ящика](styles-used-by-mfc.md#message-box-styles) к коробке. Если вы не указали этот параметр, по умолчанию MB_OK.

*nMessageID*<br/>
Упоняет идентификатор ресурса (запись строки таблицы) сообщения для отображения, если объект исключения не имеет сообщения об ошибке. Если 0, отображается сообщение "Сообщение об ошибке не доступно".

### <a name="return-value"></a>Возвращаемое значение

Значение; `AfxMessageBox` в противном случае 0, если не хватает памяти для отображения окна сообщений. Овозможных значениях возврата можно ознакомиться на [AfxMessageBox.](cstring-formatting-and-message-box-display.md#afxmessagebox)

### <a name="example"></a>Пример

Вот пример использования `CException::ReportError`. Для другого примера [CATCH](exception-processing.md#catch)см.

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

## <a name="see-also"></a>См. также раздел

[Класс CObject](cobject-class.md)<br/>
[Диаграмма иерархии](../hierarchy-chart.md)<br/>
[Обработка исключений](exception-processing.md)<br/>
[Как я: Создайте свои собственные индивидуальные классы исключений](https://go.microsoft.com/fwlink/p/?linkid=128045)
