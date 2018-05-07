---
title: CException-класс | Документы Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-mfc
ms.topic: reference
f1_keywords:
- CException
- AFX/CException
- AFX/CException::CException
- AFX/CException::Delete
- AFX/CException::ReportError
dev_langs:
- C++
helpviewer_keywords:
- CException [MFC], CException
- CException [MFC], Delete
- CException [MFC], ReportError
ms.assetid: cfacf14d-bfe4-4666-a5c7-38b800512920
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: a152c55944fca5fa858c148c009ef6301ff0f762
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: ru-RU
ms.lasthandoff: 05/04/2018
---
# <a name="cexception-class"></a>CException-класс
Базовый класс для всех исключений библиотеки классов Microsoft Foundation.  
  
## <a name="syntax"></a>Синтаксис  
  
```  
class AFX_NOVTABLE CException : public CObject  
```  
  
## <a name="members"></a>Участники  
  
### <a name="public-constructors"></a>Открытые конструкторы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CException::CException](#cexception)|Создает объект `CException`.|  
  
### <a name="public-methods"></a>Открытые методы  
  
|Имя|Описание|  
|----------|-----------------|  
|[CException::Delete](#delete)|Удаляет `CException` объекта.|  
|[CException::ReportError](#reporterror)|Возвращает сообщение об ошибке в окне сообщения для пользователя.|  
  
## <a name="remarks"></a>Примечания  
 Поскольку `CException` — абстрактный базовый класс, не удается создать `CException` объектов непосредственно, необходимо создать объекты из производных классов. Если вам нужно создать свой собственный `CException`-класс стиля, используйте один из производных классов, перечисленных выше, как модель. Убедитесь, что производный класс также используется `IMPLEMENT_DYNAMIC`.  
  
 Производные классы и их описания, перечислены ниже.  
  
|||  
|-|-|  
|[CSimpleException](../../mfc/reference/csimpleexception-class.md)|Базовый класс для исключений MFC, критический с точки зрения ресурсов|  
|[CInvalidArgException](../../mfc/reference/cinvalidargexception-class.md)|Недопустимый аргумент условие исключения|  
|[CMemoryException](../../mfc/reference/cmemoryexception-class.md)|Исключение нехватки памяти|  
|[CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md)|Запрос на недопустимую операцию|  
|[CArchiveException](../../mfc/reference/carchiveexception-class.md)|Исключения для конкретных архива|  
|[CFileException](../../mfc/reference/cfileexception-class.md)|Исключение файлов|  
|[CResourceException](../../mfc/reference/cresourceexception-class.md)|Ресурс не найден или не создаваемыми в Windows|  
|[COleException](../../mfc/reference/coleexception-class.md)|Исключения OLE|  
|[CDBException](../../mfc/reference/cdbexception-class.md)|Исключения базы данных (то есть исключение условия, возникающие для классов баз данных MFC на основе на Open Database Connectivity)|  
|[COleDispatchException](../../mfc/reference/coledispatchexception-class.md)|Исключения OLE диспетчеризации (автоматизация)|  
|[CUserException](../../mfc/reference/cuserexception-class.md)|Исключение, которое указывает, что ресурс не найден|  
|[CDaoException](../../mfc/reference/cdaoexception-class.md)|Доступ к данным объекта исключение (то есть исключения условия, возникающие для классов DAO)|  
|[CInternetException](../../mfc/reference/cinternetexception-class.md)|Исключение Интернета (то есть, условия возникновения исключений связи для классов в Интернете).|  
  
 Эти исключения, предназначены для использования с [THROW](exception-processing.md#throw), [THROW_LAST](exception-processing.md#throw_last), [повторите](exception-processing.md#try), [перехватывать](exception-processing.md#catch), [and_catch](exception-processing.md#and_catch), и [end_catch](exception-processing.md#end_catch) макросы. Дополнительные сведения об исключениях см. в разделе [обработки исключений](exception-processing.md), или обратитесь к статье [обработки исключений (MFC)](../exception-handling-in-mfc.md).  
  
 Для перехвата определенного исключения, используйте соответствующий производный класс. Для типов перехватывать все исключения, используйте `CException`, а затем используйте [CObject::IsKindOf](cobject-class.md#iskindof) для различения `CException`-производные классы. Обратите внимание, что `CObject::IsKindOf` работает только для классов, объявленные с [IMPLEMENT_DYNAMIC](run-time-object-model-services.md#implement_dynamic) макрос, чтобы воспользоваться преимуществами проверки динамического типа. Любой `CException`-производного класса, который вы создаете следует использовать `IMPLEMENT_DYNAMIC` макрос, слишком.  
  
 Сведения об исключениях, пользователю можно сообщить путем вызова [GetErrorMessage](cfileexception-class.md#geterrormessage) или [ReportError](#reporterror), двух, работающие с любой из функций-членов `CException`производных классах.  
  
 Если исключение перехватывается по один из макросов, `CException` объект автоматически удаляется, не удаляйте его самостоятельно. Если исключение перехватывается с помощью **перехватывать** ключевое слово, не удаляется автоматически. См. в статье [обработки исключений (MFC)](../exception-handling-in-mfc.md) Дополнительные сведения о том, когда для удаления объекта сведения.  
  
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
 *b_AutoDelete*  
 Укажите **TRUE** Если память для `CException` выделении объекта в куче. Это приведет к `CException` объект для удаления при **удалить** функция-член вызывается для удаления исключение. Укажите **FALSE** Если `CException` объект в стеке или — это глобальный объект. В этом случае `CException` объекта не будут удалены при **удалить** вызвать функцию-член.  
  
### <a name="remarks"></a>Примечания  
 Как правило, никогда не потребуется непосредственно вызвать этот конструктор. Функция, которая создает исключение следует создать экземпляр `CException`-производного класса и вызовите его конструктору, или она должна использовать один из MFC создать исключение функции, такие как [AfxThrowFileException](exception-processing.md#afxthrowfileexception), чтобы создавать предопределенные типа. В этой документации предоставляется только для полноты информации.  
  
##  <a name="delete"></a>  CException::Delete  
 Эта функция проверяет **CException** объект был создан в куче, и если да, вызывает **удалить** оператор в объекте.  
  
```  
void Delete();
```  
  
### <a name="remarks"></a>Примечания  
 При удалении **CException** , используйте **удалить** функция-член для удаления исключение. Не используйте **удаление** оператор напрямую, так как `CException` объект может быть глобального объекта или были созданы в стеке.  
  
 Можно указать, должен ли объект удален, при создании объекта. Дополнительные сведения см. в разделе [CException::CException](#cexception).  
  
 Необходимо вызвать **удаление** при использовании C++ **повторите**- **перехватывать** механизм. При использовании макросов MFC **ПОВТОРИТЕ** и **ПЕРЕХВАТЫВАТЬ**, а затем эти макросы автоматически вызывает эту функцию.  
  
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
 Вызовите эту функцию-член для отчета текст сообщения об ошибке в окне сообщения для пользователя.  
  
```  
virtual int ReportError(
    UINT nType = MB_OK,  
    UINT nMessageID = 0);
```  
  
### <a name="parameters"></a>Параметры  
 `nType`  
 Задает стиль окна сообщения. Примените любое сочетание [стили окна сообщений](styles-used-by-mfc.md#message-box-styles) в поле. Если этот параметр не задан, по умолчанию используется **MB_OK**.  
  
 *nMessageID*  
 Указывает идентификатор ресурса (записи в таблице строк) сообщение, отображаемое, если объект исключения не имеет сообщение об ошибке. Если значение равно 0, сообщение «отсутствует сообщение об ошибке недоступны» отображается.  
  
### <a name="return-value"></a>Возвращаемое значение  
 `AfxMessageBox` Значение; в противном случае значение 0, если не хватает памяти для отображения в окне сообщения. В разделе [AfxMessageBox](cstring-formatting-and-message-box-display.md#afxmessagebox) для возможные возвращаемые значения.  
  
### <a name="example"></a>Пример  
 Ниже приведен пример использования `CException::ReportError`. Другой пример, см. пример для [ПЕРЕХВАТЫВАТЬ](exception-processing.md#catch).  
  
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
 [CObject-класс](cobject-class.md)   
 [Диаграмма иерархии](../hierarchy-chart.md)   
 [Обработка исключений](exception-processing.md)   
 [Практические советы. Создание собственных классах пользовательское исключение](http://go.microsoft.com/fwlink/p/?linkid=128045)


